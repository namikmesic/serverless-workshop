
## Re-deploy your application
```bash
npm install
npm install --save aws-sdk body-parser
serverless deploy --verbose
export BASE_DOMAIN=<your-dev-endpoint>
curl -H "Content-Type: application/json" -X POST ${BASE_DOMAIN}/users -d '{"userId": "alexdebrie1", "name": "Alex DeBrie"}'
```

## Test the new functionality
```bash
curl -H "Content-Type: application/json" -X GET ${BASE_DOMAIN}/users/alexdebrie1
```
