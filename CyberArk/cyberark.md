## CyberArk Components

1. CyberArk PAM - Self-Hosted
This includes:
- Vault (EPV)
- PSM
- CPM
- PVWA

2. CyberArk PAM - SaaS
This includes:
- CyberArk Privilege Cloud tenant
    1. Web portal (PVWA-equivalent)
    2. Cloud Vault
- PAM Connector hosts (customer-hosted)


## CyberArk User Hierarchy

1. Authentication Profile
- “How identity is proven”
- Defines:
    - Authentication method
    - Source of Identity

2. User / Group
- “Who is requesting access”
- Defines:
    - Individual identity (user)

3. Role
- “What permissions you are assigned”
- Defines:
    - A bundle of permissions
    - Mapped to business functions (Admin, Operator, Auditor)
- Roles are linked to:
    - Safes
    - Accounts
    - Platforms
    - Workflows

4. Policy
- “How access behaves and under what conditions”
- Defines:
    - Conditions
    - Controls
    - Enforcement
Includes:
    - Approval requirements
    - MFA enforcement
    - Session recording
    - Password rotation rules
    - Command restrictions


