# Authentication Method

Auth methods are the components in Vault that perform authentication and are responsible for assigning identity and a set of policies to a user. 

In most cases, Vault will delegate the authentication administration and decision to the external auth method (e.g., AWS, GitHub, Kubernetes, Microsoft Azure, ...).

Auth methods can be enabled/disabled using:

```
vault auth enable userpass
```

By default, all auth methods are mounted underneath the auth/ prefix.

For example, if you enable "github", then you can interact with it at auth/github. 

However, this path is customizable, allowing users with advanced use cases to mount a single auth method multiple times. For example:
```
vault auth enable -path=my-login userpass
```


## 1 - AppRole

The approle auth method allows machines or apps to authenticate with Vault-defined roles using `role_ID` and `secret_ID`.

Role: **Operator**

Path: auth/approle/role/...

0. Create token policy
```
vault policy write payments-read - <<EOF
path "secret/data/payments/*" {
  capabilities = ["read"]
}
EOF
```

1. Enable the AppRole auth method
```
vault auth enable approle
```
2. Create a role
```
vault write auth/approle/role/my-role \
    token_policies="payments-read" \
    token_ttl=20m \
    token_max_ttl=30m
```
3. Get `role_ID` and `secret_id` via:
```
# Get role_ID
vault read auth/approle/role/my-role/role-id

# Get secret_ID
vault write -f auth/approle/role/my-role/secret-id
```

Role: **Deveper**

Path: auth/approle/login

1. Get role_ID and secret_ID, and draft API call to authenticate to vault:
```
curl \
    --request POST \
    --data '{"role_id":"988a9df-...","secret_id":"37b74931..."}' \
    http://127.0.0.1:8200/v1/auth/approle/login
```


## 2 - AWS



## 3 -TLS

## 4 - Active Directory



