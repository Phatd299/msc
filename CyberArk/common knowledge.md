## CyberArk Components

1. CyberArk PAM - Self-Hosted

    At the minimum requirement, this includes:
    - Vault (EPV)
    - PSM
    - CPM
    - PVWA

2. CyberArk PAM - SaaS

    This At the minimum requirement, this includes:
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

2. User

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

### When Identity Setup:
1. Create a Authentication Profile
2. Create a Policy that map to Role(s)
3. Authentication Profile is applies to the Policy
4. Users are added to Role


## CyberArk roles

At minimum, CyberArk should have 3 roles:

1. PAM Adminstrator

    - Create Safes
    - Define Platforms
    - Configure CPM / PSM / PSMP
    - Manage policies
    - Vault-level administration

2. Safe Owner

    - Manage Safe members
    - (Optionally) onboard application-owned accounts
    - View audits for their Safe

3. End-user - Privilege user

    - Launch sessions via PSM / PSMP
    - View their own session history

## CyberArk priviledge account provision

Safe

Platform

Account



