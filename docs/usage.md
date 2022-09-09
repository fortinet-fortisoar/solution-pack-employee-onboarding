| [Home](../README.md) |
|----------------------|

# Usage

Refer to [Simulate Scenario Documentation](https://github.com/fortinet-fortisoar/solution-pack-soc-simulator/tree/develop) to understand how to simulate and reset scenarios.

To understand the process FortiSOAR follows to respond to **Automated Employee Onboarding**, we have included a scenario &mdash; **Employee On/Off-Boarding** with this solution pack. Refer to following modes of operation to understand how this solution pack's automation addresses your needs.

## Simulation mode

The simulation mode has some sample data that helps you get a better understanding of how the solution pack functions. Following steps help you use the solution pack with some included sample data.

-   Make sure the global variable **Demo mode** is set to `true`. 
-   Playbook: **Scenario - Employee On/Off Boarding** has two variables `sysUser` and `dbUser`. You can populate these variables with your preferred names in the *Configuration* step. By default, the values are `bfoghali` and `jstuart`, respectively.
-   Browse to **Simulations** > **Employee On/Off-Boarding** scenario and click **Simulate Scenario**.
-   Four Alerts are created each at an interval of 10 seconds:
    - System user Onboarding
    - System user Offboarding
    - DBA user Onboarding
    - DBA user Offboarding
- For Each alert track the associated playbooks to see what services are being provisioned based on the group defined in the user provisioning email request.

## Live mode (Real data)

To use this solution pack in a real environment, change the value of the global variable `Demo_mode` to `false`.

- To Onboard a user send an email to your designated mailbox with the following details:

  |Code|Description|
  |:-|:-|
  |`ad_username_to_create`|The username as it would appear in the Active Directory|
  |`ad_group`|The Active Directory group to which the user is being assigned|
  |`job_title`|The Job Title or the position for which the employee is hired as it appears in the Active Directory|

- These details are to be emailed in the following format:

  <blockquote>
  <strong>Subject</strong>: User <code>&lt;Employee Name&gt;</code> Onboarding<br/>
  <strong>Body</strong>:<br/>
  &emsp;&emsp;<strong>Username</strong>: <code>ad_username_to_create</code><br/>
  &emsp;&emsp;<strong>Group</strong>: <code>ad_group</code><br/>
  &emsp;&emsp;<strong>Title</strong>: <code>job_title</code><br/>
  </blockquote>
            
- To Offboard a user send an email in the following format
  <blockquote>
  <strong>Subject</strong>: User <code>&lt;Employee Name&gt;</code> Offboarding<br/>
  <strong>Body</strong>:<br/>
  &emsp;&emsp;<strong>Username</strong>: <code>ad_username_to_create</code><br/>
  &emsp;&emsp;<strong>Group</strong>: <code>ad_group</code><br/>
  </blockquote>
- Make sure the groups your users belong to have the appropriate management playbooks UUIDs in their info attribute in CSV format.

> **NOTE:** The group/resources mapping is managed via the **Info** field of the group definition within the Active Directory. The field contains the CSV of UUIDs of the management playbooks for the resources within the scope of the group. As an example, if the group grants access to SSH/Server1 and MySQL/Server2 the info field would look like the following

> `9c827fcf-53bd-403a-b3bf-406f1a27d9d8`, `0d11f906-15ea-4aa9-a665-405cd44f061f`
