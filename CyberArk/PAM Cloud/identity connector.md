## CyberArk Identity Connector

- CyberArk Identity Connector - A software package installed on a dedicated join-domain server with Active Directory / Domain Controller
    1. Install package on host
    2. Using a installer user on CyberArk
    ![alt text](../images/installer_user.png)
    - Input to the wizard
    ![alt text](../images/installer_user_wizard.png)

Note: The installer user ensure trust between the Connector host to CyberArk Identity.

- Connector Management - In order to manage the connect (e.g. healthcheck, patch,..), each Connector host must install a package - **Management Agent**
    1. Install software package on the same host (configured as Connector)
    2. Add a connector by running a script as a Local Adminstrator:
    ![alt text](../images/connector_created.png)

    ![alt text](../images/connector_manage.png)