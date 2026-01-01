## HashiCorp architecture

Prerequisite:

- At the minimum, only need 1 host to run the Vault software

### Storage Backend:

Storage Backend is a block-storage for Vault software to write encrypted data in. In the Vault context, there are expectation for:

- The storage must ensure the coordination:
    - All Vault nodes see the same state
    - Writes are serialized
- The storage must ensure failover
    - One node fails → system continues
    - Automatic leader election

There are 2 options in HashiCorp vault:

1. Using seperate product - Consul, EBS, DynamoDB,...
![alt text](storage example.png)
2. Using built-in feature within Vault binary - called as Raft (need additional configuration)
![alt text](raft example.png)

### Deploy HashiCorp Vault:

For HA purpose, on Prod, a Vault cluster should be deployed as below:

![alt text](EC2 deployment.png)

Reference:
https://github.com/hashicorp/terraform-aws-vault-enterprise-hvd


### Terraform and Identity Provider



