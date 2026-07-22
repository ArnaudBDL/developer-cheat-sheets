# AWS : API Gateway

## HTTP API

```bash
aws apigatewayv2 create-api   --name application-api   --protocol-type HTTP   --target LAMBDA_FUNCTION_ARN

aws apigatewayv2 get-apis --output table
aws apigatewayv2 get-routes --api-id API_ID
aws apigatewayv2 get-stages --api-id API_ID
```

## Lambda Permission

```bash
aws lambda add-permission   --function-name application-handler   --statement-id api-gateway-invoke   --action lambda:InvokeFunction   --principal apigateway.amazonaws.com   --source-arn 'arn:aws:execute-api:REGION:ACCOUNT_ID:API_ID/*/*'
```

Configure authentication, throttling, access logs, CORS and request validation according to the API exposure model.
