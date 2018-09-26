## What changed

If you take a look at the api configuration in serverless.yml you will see that it has changed. Now, all requests to `GET /users/:userId` will be handled by the `getUser` instance of your application, and all requests to `POST /users/` will be handled by the `createUser` instance. For any other requests, they'll be handled by the main app instance of your function.

## Re-deploy your application
```bash
serverless deploy --verbose
export BASE_DOMAIN=<your-dev-endpoint>
curl -H "Content-Type: application/json" -X POST ${BASE_DOMAIN} -d '{"userId": "alexdebrie1", "name": "Alex DeBrie"}'
```

## Test the new functionality
```bash
curl -H "Content-Type: application/json" -X GET ${BASE_DOMAIN}alexdebrie1
```
