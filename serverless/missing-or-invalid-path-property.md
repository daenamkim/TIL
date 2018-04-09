# Missing or invalid "path" property

When I tried to deploy serverless APIs an error occurred as below.

```sh
$ serverless deploy
...
Serverless: Packaging service...

  Serverless Error ---------------------------------------

  Missing or invalid "path" property in function ...
```

I was really confused what the problem is and I found it.

### Wrong case

```yml
  update:
    handler: update.main
    events:
      - http:
        path: notes/{id} # WRONG INDENT
        method: put # WRONG INDENT
        cors: true # WRONG INDENT
        authorizer: aws_iam # WRONG INDENT
```

### Good case

```yml
  update:
    handler: update.main
    events:
      - http:
          path: notes/{id}
          method: put
          cors: true
          authorizer: aws_iam
```
