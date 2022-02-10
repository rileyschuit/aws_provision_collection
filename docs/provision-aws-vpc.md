## PROVISION-AWS-IAM

#### SUMMARY:

An ansible role that can be used for configuring VPC(s).  It detects the returned values to complete all the steps

Required list structure example:

```
vpc:
  - name: Development-Stage
    region: us-east-1
    cidr_block: 192.168.0.0/16
    tags:
      Environment: Development
      Tier: Web
    igw: True
    subnets:
      - { "az": "us-east-1a", "subnet": "192.168.1.0/24" }
      - { "az": "us-east-1b", "subnet": "192.168.2.0/24" }
    sec_group:
      - proto: tcp
        from_port: 80
        to_port: 80
        cidr_ip: 0.0.0.0/0
      - proto: tcp
        from_port: 443
        to_port: 443
        cidr_ip: 0.0.0.0/0
      - proto: tcp
        from_port: 22
        to_port: 22
        cidr_ip: 0.0.0.0/0
      - proto: icmp
        from_port: 8 # icmp type, -1 = any type
        to_port:  -1 # icmp subtype, -1 = any subtype
        cidr_ip: 0.0.0.0/0
```

TODOs:

- Security Groups
