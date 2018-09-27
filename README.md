## Start local environment
```bash
 npm install --save-dev serverless-offline
 npm install --save-dev serverless-dynamodb-local
 serverless dynamodb install
 serverless offline start
 ```

## Test your app locally
```bash
## See if your endpoint is okay.
 curl http://localhost:3000/
# Write user
curl -H "Content-Type: application/json" -X POST http://localhost:3000/users -d '{"userId": "alexdebrie1", "name": "Alex DeBrie"}'

# Retrieve user
curl -H "Content-Type: application/json" -X GET http://localhost:3000/users/alexdebrie1

# Invoke app function 'Hello Wolrd' locally
export IS_OFFLINE=true # Make sure you have this set up in your new terminal window
export STAGE=<your-name> # Make sure serverless is looking at the same application instance

serverless invoke local --function createUser --path test_events/create_user.json
# Invoke create user function

```

## Check changes in local dynamodb
```bash
aws dynamodb list-tables --endpoint-url http://localhost:8000
aws dynamodb scan --table-name $YOUR_TABLE_NAME --endpoint-url http://localhost:8000
```

There are may aws service we can run locally: https://github.com/atlassian/localstack
