
# Serverless Workshop
This repository aims to help you comprehend the usage of the [serverless framework](https://www.serverless.com/) and determine its suitability for your particular use case.

## Steps to Follow for Participating in the Workshop
To understand the code changes that introduce new features and functionalities, it is recommended that you start by checking out the first branch and completing the objective on your own. Afterward, you can proceed to the next branch. The git diff feature can be utilized to identify the specific changes made to the codebase, thereby facilitating an easier understanding of the process.

### Branches
1. [Serverless Workshop Part 1 - sls](https://github.com/namikmesic/serverless-workshop/tree/part_1_sls)
- Install and configure serverless
- Deploy simple application and check your AWS cloudformation stacks to see result
- Test your application

1. [Serverless Workshop Part 2 - sls](https://github.com/namikmesic/serverless-workshop/tree/part_2_sls)
- Add dynamo db table with REST-like endpoints
- Create few endpoints (Create & List users)
- Add proper IAM permissions to your lambda function
- Pass the table name as environment var, so it's unique for each deployment stage
- Pass the stage name as environment var for the same reasons
1. [Serverless Workshop Part 3 - sls](https://github.com/namikmesic/serverless-workshop/tree/part_3_sls)
- Set path specific routing for different api calls (Dedicated API endpoint)
- Discuss benefits and downsides of each approach
1. [Serverless Workshop Part 4 - sls](https://github.com/namikmesic/serverless-workshop/tree/part_4_sls)
- Start local instance of your application (Api gateway & Lambda)
- Start local instance of dynamodb and use it for testing
- Understand how to test your app offline with test events, invoke functions etc.
- Understand how to read and check changes made to local db and some additional features.
1. [Serverless Workshop Part 5 - sls](https://github.com/namikmesic/serverless-workshop/tree/part_5_sls)
- Understand how to add monitoring to your lambda functions
- Understand how to protect your api with API key
- Understand different ways of protecting your API endpoints
- Test monitoring and API keys in action
1. [Serverless Workshop Part 6 - sls](https://github.com/namikmesic/serverless-workshop/tree/part_6_sls)
- Create gitlab-ci.yml
- Understand how it works for dev and prod environments


