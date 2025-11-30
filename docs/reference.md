# Reference

Complete reference documentation for Cloudeval.

## API Reference

### Core Functions

#### `evaluate()`

Evaluate cloud resources against best practices.

**Parameters:**
- `resource` (str): Resource identifier
- `rules` (list): List of rules to apply

**Returns:**
- `dict`: Evaluation results

**Example:**
```python
from cloudeval import evaluate

results = evaluate(
    resource="my-resource",
    rules=["security", "cost-optimization"]
)
```

## Configuration

### Configuration File

Cloudeval uses a configuration file to define evaluation rules and settings.

```yaml
rules:
  - security
  - cost-optimization
  - reliability
```

## Rules

### Security Rules

Rules related to security best practices.

### Cost Optimization Rules

Rules for optimizing cloud costs.

### Reliability Rules

Rules for ensuring reliability and availability.

