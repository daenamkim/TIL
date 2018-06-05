# Fail to Delete A Bucket

When you faced an error on deleting a bucket (like beanstalk) as followed in AWS S3.

`Operation failed Delete objects 100% Successful Delete bucket Failed`


If you really want ot delete the bucket then remove json below.

- S3 > YOUR BUCKET > Permissions

```json
...
{
    "Sid": "eb-58950a8c-feb6-11e2-89e0-******7d041b",
    "Effect": "Deny",
    "Principal": {
        "AWS": "*"
    },
    "Action": "s3:DeleteBucket",
    "Resource": "arn:aws:s3:::elasticbeanstalk-us-east-1-******481579"
}
```

It's for protection of deletion.
