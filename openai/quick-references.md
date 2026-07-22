# OpenAI : Quick References

## Request pattern

```javascript
const response = await client.responses.create({
  model: "MODEL_NAME",
  input: "Your instruction"
});
console.log(response.output_text);
```

## Structured output pattern

```json
{
  "type": "object",
  "properties": {
    "result": { "type": "string" }
  },
  "required": ["result"],
  "additionalProperties": false
}
```

## Operational checklist

```text
Keep API keys outside source control
Set request timeouts
Handle rate limits and transient errors
Validate structured responses
Log identifiers without sensitive content
Track token usage and cost
```
