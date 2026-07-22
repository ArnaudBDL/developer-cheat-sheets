# AWS : Lambda

## Functions

```bash
zip function.zip index.mjs

aws lambda create-function   --function-name application-handler   --runtime nodejs22.x   --role EXECUTION_ROLE_ARN   --handler index.handler   --zip-file fileb://function.zip

aws lambda get-function --function-name application-handler
aws lambda invoke --function-name application-handler response.json
aws lambda update-function-code   --function-name application-handler   --zip-file fileb://function.zip
```

## Configuration and Logs

```bash
aws lambda update-function-configuration   --function-name application-handler   --timeout 30 --memory-size 512

aws logs tail /aws/lambda/application-handler --follow
```

Give the execution role only the permissions required by the function and keep secrets in an approved secrets service rather than environment files or source code.
