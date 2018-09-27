
## Serverless Workshop Part 4 - sls

## Objectives
- Start local instance of your application (Api gateway & Lambda)
- Start local instance of dynamodb and use it for testing
- Understand how to test your app offline with test events, invoke functions etc.
- Understand how to read and check changes made to local db and some additional features.

## Step 1 - Check updates we made
- Check `serverless.yml` for plugins we added and understand how they work
- Check changes we made to `index.js` to support local dynamodb

## Step 2 - Start your application locally
Install dependencies
```bash
npm install --save-dev serverless-offline
npm install --save-dev serverless-dynamodb-local

```
Install local dynamodb instance
```bash
serverless dynamodb install
 ```
Finally, spin it up:
```bash
serverless offline start
```

## Step 3 - Test your app locally
Check if your application works
```bash
## See if your hello world posts
 curl http://localhost:3000/
```
Check if you can create and list users locally
```bash
# Write user
curl -H "Content-Type: application/json" -X POST http://localhost:3000/users -d '{"userId": "alexdebrie1", "name": "Alex DeBrie"}'

# Retrieve user
curl -H "Content-Type: application/json" -X GET http://localhost:3000/users/alexdebrie1

```
Check information about our deployed app
```bash
# Use `serverless info` or  `serverless deploy list functions` to find out info about your functions
serverless info
serverless deploy list functions
```
Invoke `createUser` function locally
```bash
# Invoke createUser function locally
export IS_OFFLINE=true # Make sure you have this, if you're using different terminal window when invoking functions manually.
export STAGE=<your-name> # Same goes for STAGE

serverless invoke local --function createUser --path test_events/create_user.json
```

## Step 4 - Check changes in local dynamodb
List local dynamodb tables
```bash
aws dynamodb list-tables --endpoint-url http://localhost:8000
```
Scan your database and make sure users you created are there
```bash
export TABLE_NAME=<your-table-name>
aws dynamodb scan --table-name $TABLE_NAME --endpoint-url http://localhost:8000
```

## Step 5 - Get acquanted with other aws services you can run locally
There are may aws service we can run locally. See here. - https://github.com/atlassian/localstack
