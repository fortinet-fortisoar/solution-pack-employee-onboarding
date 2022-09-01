| [Home](https://github.com/fortinet-fortisoar/solution-pack-connector-health-mointoring/blob/release/1.0.0/README.md) |
|--------------------------------------------|

# Contents

The **Employee Onboarding** solution pack contains the following resources.

## Connectors

|**Name**|**Description**|
| :- | :- |
| Excahnge | The Exchange connector provides a robust, platform-independent, and simple interface for communicating with Microsoft Exchange 2007-2016 Server or Office 365 using Exchange Web Services (EWS). |
| Microsoft Active Directory | Helps directly query AD to retrieve information about users, groups, and computers, in an organization, by using the Lightweight Directory Access Protocol (LDAP). |
| MySQL | MySQL Connector allows different database operations with MySQL. |
| SSH | Steps that use an ssh connection. Including sftp and remote code execution. |

## Global Variable

|**Name**|**Description**|
| :- | :- |
|  Demo_mode  |  Set to true for Simulation Mode.  |
| EOF_SYS_User | The variable holds the name of the newly provisioned or deprovisioned user for system. |
| EOF_DB_User | The variable holds the name of the newly provisioned or deprovisioned user for DB. |

## Playbook Collection

|Playbook Collection Name |
| :- |
| 02 - Use Case - Employee On/Off-Boarding |

**Playbook Name**|**Description**|
| :- | :- |
| Onboard Employee  |  Onboard an employee based on the received instruction  |
| Offboard Employee |  Offboard an employee based on the received instruction  |
| DBAdmins User Onboarding Request | Request to Create user Engineer1 member of DBAdmins |
| DBAdmins User Offboarding Request | Request to Offboard  user Engineer1 member of DBAdmins |
| SysAdmin User Onboarding Request | Request to Onboard user Engineer1 member of SysAdmins | 
| SysAdmin User Offboarding Request | Request to Offboard user member of SysAdmins |
| Create Users on Active Directory | Creates user and associate it with a group |
| Disable Users on Active Directory | Disables user on AD|
| Create SSH User on Solar-Web-2 Server | Provisionuser access on Elab server |
| Disable SSH User on Solar-Web-2 Server | Deprovision user access on Elab server |
| Create MySQL User on FR-BKDB-1 Server | Creates a MySQL user and grant access to DB |
| Delete MySQL User on FR-BKDB-1 Server | Deletes MySQL user |
| Create Mailbox on Exchange | Creates a mailbox for a new AD user |
| Manage SSH Users on Solar-Web-2 Server | Creates/Disables user profiles on ETLab WebServer |
| Manage MySQL Users on FR-BKDB-1 Server | Creates/Disables user profiles on ETLab WebServer |

>**Warning:** We recommend that you clone these playbooks before customizing to avoid loss of information while upgrading the solution pack.
