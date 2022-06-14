# Employee On/Off-Boarding
[![Solution Pack Video](https://img.youtube.com/vi/ytVDEOY432A/0.jpg)](https://www.youtube.com/embed/ytVDEOY432A)

[Solution Pack Video Introduction](https://www.youtube.com/embed/ytVDEOY432A)
                                   
## 1) Overview
It is typical for large organizations to have an important turn over with several employees leaving and joining every day. While most access is managed by IAM/SSO several systems (especially legacy ones) still require local configuration to grant access for the new users or disable access for those who left.
FortiSOAR Employee On/Off Boarding solution pack helps automating this process by provisioning the access for new employees on the systems they have access to and disabling that access for the ones leaving the organization.
The mapping of each user access scope is done via Active Directory, where the group object holds the list of resources the members of the group can access.
Typically user provisioning order comes from HR, in this simulation we assume it comes via Email. The required attributes for new users are:

- Username
- Group
- Title

FortiSOAR will: 
 - Create the user on *Active Directory*
 - Create a mailbox for the user on *Microsoft Exchange*
 - Read the group access scope from *Active Directory* and provision access for the user on all systems part of the above scope

 > The group/resources mapping is managed via the *Info* field of the group definition within *Active Directory*. the field contains the CSV of UUIDs of the management playbooks for the resources within the scope of the group. As an example, if the group grants access to SSH/Server1 and MySQL/Server2 the info field would look like: `9c827fcf-53bd-403a-b3bf-406f1a27d9d8,0d11f906-15ea-4aa9-a665-405cd44f061f` 

If the action is to **deprovision** similar logic is applied except the action would be either to disable the user or delete it depending on the target system

## 2) Prerequisites

### 2.1) Generic Prerequisites:
- SOAR Essentials Solution Pack

### 2.2) For Simulation mode (Fake mock data):
- Make sure your global variable: `Demo_mode` is set to `true` (Playbook editors > Tools > Global Variables)
- Make sure your global variable: `EOF_SYS_User` is set to a username of your choice (Playbook editors > Tools > Global Variables). The variable holds the name of the newly provisioned or deprovisioned user
- Make sure your global variable: `EOF_DB_User` is set to a username of your choice (Playbook editors > Tools > Global Variables)
- FortiSOAR SOC Simulator Connector configured (1.0.9+)
- It is recommended to have a working SMTP connector to receive tasks notifications

### 2.3) For Live mode (Real data):
- MS Exchange/SMTP Connectors configured with your MS Exchange parameters (To receive instruction emails and send notifications)
- AD Connector configured with your DC parameters (To run AD related actions)
- MySQL/SSH server(s) to act as resources

> All Credentials used with the above connectors must have the required privileges to perform the actions they are meant to do (add user, disable user...etc)

> You can customize the use case for your environment by adding 3 playbooks for each service: Provision, Deprovision , Management the latter is only used as a wrapper for the first two. Open any examples of the existing services to see how is it done


### 3) Installation/Deployment:
- Download the repo's zip from this page, click on: **Code > Download ZIP** and save the ZIP file to your workstation
- On FortiSOAR Browse to **Content Hub > Manage** and use the **Upload** then drag and drop the Solution Pack's zip file

### 4) Simulation Steps:
#### 4.1) For Simulation mode (Fake mock data):
- Edit global variables: EOF_SYS_User and EOF_DB_User and populate them with names of your choice
- Browse to Simulations, select the scenario and click **Run scenario**
- (4) Alerts will be created at 30 seconds interval:
    - System user Onboarding
    - System user Offboarding
    - DBA user Onboarding
    - DBA user Offboarding
- For Each alert track the associated playbooks to see what services are being provisioned based on the group defined in the user provisioning email request 

#### 4.2) For Live mode (Real data):
- To Onboard a user send an email to your FortiSOAR mailbox with:
    - Subject: user ... onboarding
    - body:
```
Username: ad_username_to_create
Group: ad_group
Title: job_title
```
- To Offboard a user send an email to your FortiSOAR mailbox with:
    - Subject: user ... offboarding
    - body:
```
Username: ad_username_to_create
Group: ad_group
```
- Make sure the groups your users belong to have the appropriate management playbooks UUIDs in their info attribute in CSV format


