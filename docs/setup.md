| [Home](https://github.com/fortinet-fortisoar/solution-pack-employee-onboarding/blob/release/1.0.0/README.md) |
|--------------------------------------------|

# Installation

1. To install a solution pack, click **Content Hub** > **Discover**.
2. From the list of solution pack that appears, search for and select **Automated Employee Onboarding**.
3. Click the **Automated Employee Onboarding** solution pack card.
4. Click **Install** on the bottom to begin installation.

## Prerequisites

The **Automated Employee Onboarding** solution pack depends on the following solution packs that are installed automatically &ndash; if not already installed.

| **Solution Pack Name** | **Purpose**   |
| :--------------------- | :--------------------------------------- |
|  SOAR Framework  | Require for Incident Response modules  |
|  SOC Simulator  | Require for Scenario Module and SOC Simulator connector  |

# Configuration

For optimal performance of **Automated Employee Onboarding** solution pack, you can install and configure the connectors that help with the following:

>**Example**:
>* **Exchange:** To create a mailbox for user, for configuration refer to [Configuring Exchange Connector](https://docs.fortinet.com/document/fortisoar/4.0.0/exchange/295/exchange-v4-0-0)
>* **Active Directory:** To enable and disable user, for configuration refer to [Configuring Active Directory Connector](https://docs.fortinet.com/document/fortisoar/2.2.0/active-directory/154/active-directory-v2-2-0)
>   *    **Note:** LDAPS has to be used while configuring the AD conenctor, this is required for all password operations.
>* **SSH connector:** To configure and use the SSH connector, refer to [Configuring SSH Connector](https://docs.fortinet.com/document/fortisoar/2.1.1/ssh-connector/329/ssh-connector-v2-1-1)
>* **MySQL:** To configure and use the MySQL connector, refer to [Configuring MySQL Connector](https://docs.fortinet.com/document/fortisoar/1.0.0/mysql/1/mysql-v1-0-0)

> **Note:** All Credentials used with the above connectors must have the required privileges to perform the actions they are meant to do (add user, disable user...etc)