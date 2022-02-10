## PROVISION-AWS-S3

#### SUMMARY:

An ansible role that can be used for configuring VPC(s).  It detects the returned values to complete all the steps

Required list structure example:

```
s3_buckets:
  just_an_example:
    bucket_name: sample_bucket

  host_example:
    bucket_name: mysupercoolwebsite.com
    region: us-east-1
    policy_type: web_hosting
```
