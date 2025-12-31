## CyberArk Identity Connector

- CyberArk Identity Connector - A software package installed on a dedicated join-domain server with Active Directory / Domain Controller
    1. Install package on host
    2. Using a service account on CyberArk
    ![alt text](image-2.png)
    - Input to the wizard
    ![alt text](image-3.png)

Note: The installer user ensure trust between the Connector host to CyberArk Identity.

- Connector Management - In order to manage the connect (e.g. healthcheck, patch,..), each Connector host must install a package - **Management Agent**
    1. Install software package on the same host (configured as Connector)
    2. Add a connector by running a script as a Local Adminstrator:
    ![alt text](image-4.png)

    ![alt text](image-5.png)