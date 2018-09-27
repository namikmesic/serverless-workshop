
## Serverless Workshop Part 5 - sls

## Objectives
- Understand how to add monitoring to your lambda functions
- Understand how to protect your api with API key
- Understand different ways of protecting your API endpoints
- Test monitoring and API keys in action

## Step 1 - Check updates we made
- Check `serverless.yml` file and take a look monitoring configuration
- Check `serverless.yml` for `apiKeys` config and take a look difference `createUser` endpoint has.


## Step 2 - Re-deploy your application with updated config
Install dependencies
```bash
npm install serverless-plugin-aws-alerts --save-dev
```
Configure e-mail and deploy the app
```bash
export EMAIL=<your-e-mail>
serverless deploy -v
```
## Step 3 - Test new features
Test api protection

```bash
# Try to create user without API key and see what happens
curl -X POST $BASE_DOMAIN/users -H 'Content-Type: application/json' -d  '{"userId": "testuser", "name": "testing tester"}'

# Create user with api key provided
curl -X POST $BASE_DOMAIN/users -H 'Content-Type: application/json' -H 'x-api-key: <your-api-key>' -d  '{"userId": "testuser", "name": "testing tester"}'

# List User should work without api key because it's not protected
# You can protect this endpoint simply by making it private
curl -H "Content-Type: application/json" -X GET ${BASE_DOMAIN}/users/testuser
```
curl -X POST $BASE_DOMAIN/users -H 'Content-Type: application/json' -H 'x-api-key: <your-api-key>' -d  '{"userId": "testuser", "name": "testing tester"}'
Test monitoring
- Check your e-mail after deploying the app, and accept subscription
- Break something in the function and re-deploy function

```bash
# For example
# First edit intex.js and break it somewhere around creating user

# Now deploy the function
serverless deploy function -f createUser

# Now test it few times
curl -X POST $BASE_DOMAIN/users -H 'Content-Type: application/json' -H 'x-api-key: <your-api-key>' -d  '{"userId": "testuser", "name": "testing tester"}'

# Soon you should be receiveng an e-mail that something went wrong with your lambda function
```
