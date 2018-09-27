# Serverless Workshop Part 1

## Objectives
- Install and configure serverless
- Deploy simple application and check your AWS cloudformation stacks to see result

#### Step 1 - Set up Environment
Install and confugre [npm](https://docs.npmjs.com/getting-started/installing-node)

#### Step 2 - Install and configure serverless
Install serverless
```bash
npm install -g serverless
```
Configure your AWS credentials, please make sure you have admin access.

```bash
export AWS_ACCESS_KEY_ID: <your-access-key>
export AWS_SECRET_ACCESS_KEY: <your-secret-access-key>
export AWS_DEFAULT_REGION: eu-west-1
serverless config credentials --provider aws --key $AWS_ACCESS_KEY_ID --secret $AWS_SECRET_ACCESS_KEY
```
## Deploy your application
```bash
npm init -f
npm install --save express serverless-http
export STAGE=<your-name>
serverless deploy --verbose
```
