## Add some monitoring
```bash
npm install serverless-plugin-aws-alerts --save-dev
```
- Update serverless.yml with your e-mail
- Deploy application
```bash
serverless deploy -v
```
- You should now receive subscription permission from AWS (approve it)
- Now break soemething and you should receive an e-mail.
