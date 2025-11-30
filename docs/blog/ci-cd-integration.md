# Integrating Cloudeval into Your CI/CD Pipeline

**Published:** January 28, 2025  
**Author:** Cloudeval Team  
**Category:** Tutorials

## Introduction

Integrating Cloudeval into your CI/CD pipeline ensures that infrastructure changes are evaluated before deployment, catching issues early and maintaining quality standards. This guide shows you how to set up Cloudeval with popular CI/CD platforms.

## Why Integrate Cloudeval?

### Benefits

- **Early Detection**: Catch issues before they reach production
- **Consistent Standards**: Enforce best practices across all deployments
- **Automated Validation**: No manual review needed for common issues
- **Cost Control**: Prevent costly misconfigurations
- **Security**: Identify security issues in infrastructure code

## GitHub Actions Integration

### Basic Setup

Create `.github/workflows/cloudeval.yml`:

```yaml
name: Cloudeval Evaluation

on:
  pull_request:
    paths:
      - 'infrastructure/**'
      - '*.bicep'
      - '*.json'
  push:
    branches:
      - main

jobs:
  evaluate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      
      - name: Install Cloudeval
        run: pip install cloudeval
      
      - name: Run Evaluation
        run: |
          cloudeval evaluate \
            --input-path ./infrastructure \
            --rules security,cost-optimization,reliability \
            --format github-actions
        env:
          AZURE_CREDENTIALS: ${{ secrets.AZURE_CREDENTIALS }}
      
      - name: Upload Results
        uses: actions/upload-artifact@v3
        with:
          name: cloudeval-report
          path: cloudeval-report.json
```

### Advanced Configuration

#### Fail on Specific Rules

```yaml
- name: Run Evaluation
  run: |
    cloudeval evaluate \
      --input-path ./infrastructure \
      --rules security \
      --fail-on-error \
      --severity high
```

#### Generate HTML Report

```yaml
- name: Generate Report
  run: |
    cloudeval evaluate \
      --input-path ./infrastructure \
      --format html \
      --output report.html
    
- name: Publish Report
  uses: peaceiris/actions-gh-pages@v3
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}
    publish_dir: ./reports
```

## Azure Pipelines Integration

### YAML Pipeline

```yaml
trigger:
  branches:
    include:
      - main
      - develop

pool:
  vmImage: 'ubuntu-latest'

steps:
- task: UsePythonVersion@0
  inputs:
    versionSpec: '3.11'
  
- script: |
    pip install cloudeval
  displayName: 'Install Cloudeval'
  
- script: |
    cloudeval evaluate \
      --input-path $(Build.SourcesDirectory)/infrastructure \
      --rules security,cost-optimization \
      --format azure-devops \
      --output $(Build.ArtifactStagingDirectory)/report.json
  displayName: 'Run Cloudeval Evaluation'
  env:
    AZURE_CREDENTIALS: $(AZURE_CREDENTIALS)
  
- task: PublishTestResults@2
  inputs:
    testResultsFormat: 'JUnit'
    testResultsFiles: '$(Build.ArtifactStagingDirectory)/report.xml'
  
- task: PublishBuildArtifacts@1
  inputs:
    pathToPublish: '$(Build.ArtifactStagingDirectory)'
    artifactName: 'cloudeval-report'
```

## GitLab CI Integration

### `.gitlab-ci.yml`

```yaml
stages:
  - validate
  - deploy

cloudeval:
  stage: validate
  image: python:3.11
  before_script:
    - pip install cloudeval
  script:
    - cloudeval evaluate
        --input-path ./infrastructure
        --rules security,cost-optimization
        --format gitlab
        --output cloudeval-report.json
  artifacts:
    reports:
      junit: cloudeval-report.xml
    paths:
      - cloudeval-report.json
    expire_in: 1 week
  only:
    - merge_requests
    - main
```

## Jenkins Integration

### Jenkinsfile

```groovy
pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Install Cloudeval') {
            steps {
                sh 'pip3 install cloudeval'
            }
        }
        
        stage('Evaluate Infrastructure') {
            steps {
                sh '''
                    cloudeval evaluate \
                        --input-path ./infrastructure \
                        --rules security,cost-optimization \
                        --format junit \
                        --output cloudeval-report.xml
                '''
            }
        }
        
        stage('Publish Results') {
            steps {
                junit 'cloudeval-report.xml'
                archiveArtifacts 'cloudeval-report.json'
            }
        }
    }
    
    post {
        always {
            publishHTML([
                reportName: 'Cloudeval Report',
                reportDir: 'reports',
                reportFiles: 'index.html',
                keepAll: true
            ])
        }
    }
}
```

## Terraform Integration

### Pre-commit Hook

Create `.pre-commit-config.yaml`:

```yaml
repos:
  - repo: local
    hooks:
      - id: cloudeval
        name: Cloudeval Evaluation
        entry: cloudeval evaluate
        language: system
        args:
          - --input-path
          - .
          - --rules
          - security,cost-optimization
          - --fail-on-error
        files: \.(tf|bicep|json)$
```

Install:

```bash
pip install pre-commit
pre-commit install
```

## Best Practices

### 1. Use Appropriate Rule Sets

```yaml
# Development environment
rules:
  - security
  - cost-optimization

# Production environment
rules:
  - security
  - cost-optimization
  - reliability
  - compliance
```

### 2. Set Appropriate Failure Thresholds

```bash
# Fail only on high-severity security issues
cloudeval evaluate \
  --rules security \
  --fail-on-error \
  --severity high

# Warn on cost issues, fail on security
cloudeval evaluate \
  --rules security,cost-optimization \
  --fail-on security \
  --warn-on cost-optimization
```

### 3. Cache Dependencies

```yaml
# GitHub Actions
- name: Cache Python dependencies
  uses: actions/cache@v3
  with:
    path: ~/.cache/pip
    key: ${{ runner.os }}-pip-${{ hashFiles('requirements.txt') }}
```

### 4. Parallel Evaluations

```yaml
strategy:
  matrix:
    rule-set:
      - security
      - cost-optimization
      - reliability
jobs:
  evaluate-${{ matrix.rule-set }}:
    runs-on: ubuntu-latest
    steps:
      - run: cloudeval evaluate --rules ${{ matrix.rule-set }}
```

## Notification and Reporting

### Slack Integration

```yaml
- name: Notify on Failure
  if: failure()
  run: |
    curl -X POST ${{ secrets.SLACK_WEBHOOK }} \
      -d '{"text":"Cloudeval evaluation failed. Check the report."}'
```

### Email Reports

```yaml
- name: Send Email Report
  run: |
    cloudeval evaluate \
      --format email \
      --send-to team@company.com
```

## Troubleshooting

### Common Issues

**Issue:** Evaluation times out  
**Solution:** Use resource filtering or evaluate specific paths

**Issue:** Authentication failures  
**Solution:** Ensure credentials are properly configured in secrets

**Issue:** False positives  
**Solution:** Configure rule exceptions or custom rules

## Conclusion

Integrating Cloudeval into your CI/CD pipeline is straightforward and provides significant value by catching issues early. Start with basic integration and gradually add more sophisticated checks as needed.

## Resources

- [Cloudeval CLI Reference](../../reference.md#cli)
- [Rule Configuration](../../reference.md#rules)
- [GitHub Actions Examples](https://github.com/ganakailabs/cloudeval-docs/examples)

---

**Need help?** [Open an issue](https://github.com/ganakailabs/cloudeval-docs/issues) or [join our discussions](https://github.com/ganakailabs/cloudeval-docs/discussions)!

