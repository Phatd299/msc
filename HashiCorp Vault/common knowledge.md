## HashiCorp architecture

Prerequisite:

- At the minimum, only need 1 host to run the Vault software

### Storage Backend

Storage Backend is a block-storage for Vault software to write encrypted data in. In the Vault context, there are expectation for:

- The storage must ensure the coordination:
    - All Vault nodes see the same state
    - Writes are serialized
- The storage must ensure failover
    - One node fails → system continues
    - Automatic leader election

There are 2 options in HashiCorp vault:

1. Using seperate product - Consul, EBS, DynamoDB,...
![alt text](storage_example.png)

2. Using built-in feature within Vault binary - called as Raft (need additional configuration)
![alt text](raft_example.png)

### Deploy HashiCorp Vault

For HA purpose, on Prod, a Vault cluster should be deployed as below:

![alt text](EC2_deployment.png)

Reference:
https://github.com/hashicorp/terraform-aws-vault-enterprise-hvd


### Terraform and Identity Provider

#### Terraform

Terraform can be used to configure HashiCorp vault via Terraform Vault Provider

https://registry.terraform.io/providers/hashicorp/vault/latest/docs

Basically:

Terraform file (.tf file), for example:

```
resource "vault_mount" "dev-secrets" {
  path        = "dev-secrets"
  type        = "kv"
  options     = { version = "2" }
}
```

When Terraform CLI run "terraform apply", the CLI talks to Vault Provider to mount a KV secret engine to the path "dev-secret"

### Identity Provider

![alt text](Identity_provider.png)

https://developer.hashicorp.com/vault/tutorials/auth-methods/oidc-auth

The OIDC auth method can redirect a user's browser to a configured identity provider, complete a login, and then re-route the user back to Vault's UI with a newly-created Vault token.




