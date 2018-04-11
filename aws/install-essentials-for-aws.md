# Install Essentials for AWS

### AWS CLI

```sh
$ pip install awscli
$ aws configure
```

Access key ID, secret access key whose added a user in aws will be asked.

An example to add an account into cognitor user pool.

```sh
aws cognito-idp sign-up \
  --region {REGION} \
  --client-id {APP CLIENT ID IN COGNITO} \
  --username {EMAIL} \
  --password {PASSWORD}
```

An example to add confirm an account signed up.

```sh
aws cognito-idp admin-confirm-sign-up \
  --region {REGION} \
  --user-pool-id {USER POOL ID IN COGNITO} \
  --username {EMAIL}
```

### AWS API Gateway Test CLI
```sh
$ yarn global add aws-api-gateway-cli-test
```

A test example as below.

```sh
$ apig-test \
--username='{EMAIL}' \
--password='{PASSWORD}' \
--user-pool-id='{USER POOL ID IN COGNITO}' \
--app-client-id='{APP CLIENT ID IN COGNITO}' \
--cognito-region='{REGION OF COGNITO}' \
--identity-pool-id='{IDENTITY POOL ID IN API GATEWAY}' \
--invoke-url='{LAMBDA API GATEWAY URL IN LAMBDA}' \
--api-gateway-region='{REGION OF API GATEWAY}' \
--path-template='{PATH}' \
--method='{METHOD}' \
--body='{BODY}'
```

