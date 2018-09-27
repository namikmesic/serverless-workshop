## Add simple authentication to your api gateway
Check yaml for `apiKeys` configuration
## Add some monitoring
```bash
npm install serverless-plugin-aws-alerts --save-dev
export EMAIL=<your-e-mail>
serverless deploy -v
```
- You should now receive subscription permission from AWS (approve it)
- Now break something and you should receive an e-mail.
