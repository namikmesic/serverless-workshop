
## Serverless Workshop Part 2 - sls
## Objectives
- Add dynamo db table with REST-like endpoints
- Create few endpoints (Create & List users)
- Add proper IAM permissions to your lambda function
- Pass the table name as environment var, so it's unique for each deployment stage
- Pass the stage name as environment var for the same reasons

## Step 1 - Check updates we made
- Check `serverless.yml` file compared to Part 1
- Check `index.js` function compared to Part 1

Make sure it is clear what has changed and why.

## Step 2 - Re-deploy your application
Install dependencies
```bash
npm install
npm install --save aws-sdk body-parser
```

Finally re-deploy your application
```bash
export STAGE=<your-name>
serverless deploy --verbose
```

## Step 3 - Test the new functionality
```bash
export BASE_DOMAIN=<your-dev-endpoint>
# Create user
curl -H "Content-Type: application/json" -X POST ${BASE_DOMAIN}/users -d '{"userId": "alexdebrie1", "name": "Alex DeBrie"}'
# List user
curl -H "Content-Type: application/json" -X GET ${BASE_DOMAIN}/users/alexdebrie1
```
