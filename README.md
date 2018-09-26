## Set up Environment
https://docs.npmjs.com/getting-started/installing-node # Install and set-up npm
```bash
npm install -g serverless
export AWS_ACCESS_KEY_ID: <your-access-key>
export AWS_SECRET_ACCESS_KEY: <your-secret-access-key>
export AWS_DEFAULT_REGION: eu-west-1
serverless config credentials --provider aws --key AWS_ACCESS_KEY_ID --secret AWS_SECRET_ACCESS_KEY
```
## Deploy your application
```bash
npm init -f
npm install --save express serverless-http
export STAGE=<your-name>
serverless deploy --verbose
```
