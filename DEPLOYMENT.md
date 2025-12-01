# Deployment Guide

This document explains how the documentation is deployed.

## Deployment Setup

### Workflow File

The workflow is defined in `.github/workflows/docs.yaml`.

### Process

1. **Trigger**: On push to `main` branch or manual workflow dispatch
2. **Build**: 
   - Installs Python dependencies
   - Builds MkDocs documentation
   - Pushes to `gh-pages` branch
3. **Deploy**: 
   - Uses GitHub Pages Actions
   - Deploys from `gh-pages` branch

### Initial Setup

Before the first deployment, you need to:

1. **Enable GitHub Pages**:
   - Go to repository **Settings** → **Pages**
   - Source: Select **GitHub Actions**

2. **Create gh-pages branch** (if it doesn't exist):
   ```bash
   git checkout --orphan gh-pages
   git rm -rf .
   echo "# GitHub Pages" > README.md
   git add README.md
   git commit -m "Initial gh-pages branch"
   git push origin gh-pages
   git checkout main
   ```

3. **Push the workflow**:
   ```bash
   git add .github/workflows/ci.yml
   git commit -m "Add documentation deployment workflow"
   git push origin main
   ```

### After First Deployment

Once the workflow runs successfully:
- Your site will be available at: `https://ganakailabs.github.io/cloudeval/`
- Future pushes to `main` will automatically rebuild and redeploy

## Custom Domain Setup

See [CUSTOM_DOMAIN.md](docs/CUSTOM_DOMAIN.md) for instructions on setting up a custom domain.

## Local Testing

Before deploying, test locally:

```bash
# Install dependencies
pip install -r requirements.txt

# Serve locally
mkdocs serve

# Build locally (to test)
mkdocs build
```

## Troubleshooting

### Workflow fails

- Check GitHub Actions logs
- Verify Python version compatibility
- Ensure `requirements.txt` is up to date

### Site not updating

- Check if `gh-pages` branch exists
- Verify workflow has write permissions
- Check GitHub Pages settings

### Build errors

- Test locally with `mkdocs build --strict`
- Check for broken links or invalid markdown
- Review MkDocs configuration

