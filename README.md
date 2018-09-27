## Objectives
- Set path specific routing for different api calls (Dedicated API endpoint)
- Discuss benefits and downsides of each approach


## Step 1 - Check updates we made
- Check `serverless.yml` file compared to Part 2

## Re-deploy your application
```bash
serverless deploy --verbose
```

## Test the new functionality
```bash
export STAGE=<your-name>
export BASE_DOMAIN=<your-dev-endpoint>

curl -H "Content-Type: application/json" -X GET ${BASE_DOMAIN}/alexdebrie1
curl -H "Content-Type: application/json" -X POST ${BASE_DOMAIN} -d '{"userId": "alexdebrie1", "name": "Alex DeBrie"}'
```
