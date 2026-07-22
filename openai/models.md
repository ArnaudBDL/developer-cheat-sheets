# OpenAI : Models

## Model Selection

```text
Task quality
Supported modalities
Structured-output and tool support
Context requirements
Latency
Throughput limits
Input and output price
Regional or organizational availability
```

## List Models

```python
models = client.models.list()
for model in models.data:
    print(model.id)
```

## Configuration

```python
MODEL_ID = "YOUR_SELECTED_MODEL"
```

- Treat model identifiers and capabilities as configuration.
- Verify modality, endpoint and feature compatibility before deployment.
- Pin a tested model version when operational stability requires it.
- Evaluate quality, latency and cost with representative inputs.
- Maintain a controlled migration and rollback path.
