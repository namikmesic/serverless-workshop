## Add simple authentication to your api gateway
Check yaml for `apiKeys` configuration
## Add some monitoring
```bash
npm install serverless-plugin-aws-alerts --save-dev
export EMAIL=<your-e-mail>
serverless deploy -v
```
## Test if it works
```bash
export API_KEY=<your-api-key>
# Create user
curl -X POST $BASE_DOMAIN/users -H 'Content-Type: application/json' -H 'x-api-key: <your-api-key>' -d  '{"userId": "testuser", "name": "testing tester"}'

# List User
curl -H "Content-Type: application/json" -X GET ${BASE_DOMAIN}/users/testuser

```
- You should now receive subscription permission from AWS (approve it)
- Now break something and you should receive an e-mail.
