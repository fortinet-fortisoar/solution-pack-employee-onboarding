| [Home](../README.md) |
|----------------------|

# Contents

The **Automated Employee Onboarding** solution pack contains the following resources.

## Connectors

| Name                       | Description                                                                                                                                                                                      |
|:---------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Excahnge                   | The Exchange connector provides a robust, platform-independent, and simple interface for communicating with Microsoft Exchange 2007-2016 Server or Office 365 using Exchange Web Services (EWS). |
| Microsoft Active Directory | Helps directly query AD to retrieve information about users, groups, and computers, in an organization, by using the Lightweight Directory Access Protocol (LDAP).                               |
| MySQL                      | MySQL Connector allows different database operations with MySQL.                                                                                                                                 |
| SSH                        | Steps that use an ssh connection. Including sftp and remote code execution.                                                                                                                      |

## Global Variable

| Name        | Description                        |
|:------------|:-----------------------------------|
| `Demo_mode` | Set to `true` for Simulation Mode. |

## Playbook Collection

| Playbook Collection Name                 |
|:-----------------------------------------|
| 02 - Use Case - Employee On/Off-Boarding |

| Playbook Name                          | Description                                             |
|:---------------------------------------|:--------------------------------------------------------|
| Onboard Employee                       | Onboard an employee based on the received instruction.  |
| Offboard Employee                      | Offboard an employee based on the received instruction. |
| Create Mailbox on Exchange             | Creates a mailbox for a new AD user.                    |
| Create Users on Active Directory       | Creates user and associate it with a group.             |
| Disable Users on Active Directory      | Disables user on AD.                                    |
| Manage SSH Users on Solar-Web-2 Server | Creates/Disables user profiles on ETLab WebServer.      |
| Create SSH User on Solar-Web-2 Server  | Provision user access on Elab server.                   |
| Disable SSH User on Solar-Web-2 Server | Deprovision user access on Elab server.                 |
| Manage MySQL Users on FR-BKDB-1 Server | Creates/Disables user profiles on ETLab WebServer.      |
| Create MySQL User on FR-BKDB-1 Server  | Creates a MySQL user and grant access to DB.            |
| Disable MySQL User on FR-BKDB-1 Server | Deletes MySQL user.                                     |
| Scenario - Employee On/Off Boarding    | Request to Onboard/Offboard user of SysAdmin/DbAdmin    |

> **NOTE:** You can customize the use case for your environment by adding 3 playbooks for each service: Provision, Deprovision , Management the latter is only used as a wrapper for the first two. Open any examples of the existing services to see how is it done

>**WARNING:** We recommend that you clone these playbooks before customizing to avoid loss of information while upgrading the solution pack.
