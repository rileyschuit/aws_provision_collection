## Ansible Collection
### rileyschuit.aws_provision_collection

**Summary:**  A gathering of my old aws provisioning roles into a collection.  Mostly used for example sake but may help someone in the future.

**Requirements:**

| What | how | Notes|
| ----------- | ----------- |  ----------- |
| AWS_ACCESS_KEY_ID | var or set by .aws/crednentials||
|AWS_ACCESS_KEY |var or set by .aws/crednentials ||
| boto3 | pip | roles should be checking for this too |
| vpc | dict | Refer to the [doc](./docs/provision-aws-vpc.md) |
| iam | dict| Refer to the [doc](./docs/provision-aws-iam.md) |
|s3_buckets| dict | Refer to the [doc](./docs/provision-aws-s3.md)|


**Suggestions and samples:**

ansible.cfg suggestion ([documentation](https://docs.ansible.com/ansible/latest/reference_appendices/config.html#collections-paths)): 

```
[defaults]
collections_path=collections/
```

collections/requirements.yml sample:
```
collections:
  - name: rileyschuit.aws_provision_collection
```

playbook example:
```
- name: Do some cool aws stuff
  hosts: localhost
  connection: local

  roles:
    - rileyschuit.aws_provision_collection.provision-aws-vpc
    - rileyschuit.aws_provision_collection.provision-aws-iam
```

Role documentation:
[provision-aws-iam](./docs/provision-aws-iam.md)  
[provision-aws-vpc](./docs/provision-aws-vpc.md)