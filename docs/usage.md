| [Home](https://github.com/fortinet-fortisoar/solution-pack-employee-onboarding/blob/release/1.0.0/README.md) |
|--------------------------------------------|

# Usage

Refer to [Simulate Scenario documentation](https://github.com/fortinet-fortisoar/solution-pack-soc-simulator/tree/release/1.0.2) to understand how to simulate and reset scenarios.

To understand the process FortiSOAR follows to respond to **Automated Employee Onboarding**, we have included a scenario &mdash; **Employee On/Off-Boarding** with this solution pack. Refer to below mode to understand how this solution pack automation addresses your needs.

## Simulation mode (Fake mock data)
    
*   Make sure the global variable **Demo mode** is set to `true`. 
*   Playbook: **Scenario - Employee On/Off Boarding** have two variables **sysUser** and **dbUser** which can be populate with names of your choice in configuration step. By default value is `bfoghali` and `jstuart` respectively.


*   Browse to Simulations, select the **Employee On/Off-Boarding** scenario and click **Simulate Scenario**.
*   Four Alerts are created within the interval of 10 seconds:
 
        System user Onboarding
        System user Offboarding
        DBA user Onboarding
        DBA user Offboarding
*    For Each alert track the associated playbooks to see what services are being provisioned based on the group defined in the user provisioning email request.

## Live mode (Real data)

**Note:** Make sure the global variable **Demo mode** is set to `false`.
*   To Onboard a user send an email to your Designated mailbox with:

        Subject: User <Employee Name> Onboarding
        Body:
            Username: ad_username_to_create
            Group: ad_group
            Title: job_title
            
*   To Offboard a user send an email to your Designated mailbox with:
    
        Subject: User <Employee Name> Offboarding
        Body:
            Username: ad_username_to_create
            Group: ad_group

* Make sure the groups your users belong to have the appropriate management playbooks UUIDs in their info attribute in CSV format.
> **Note:** The group/resources mapping is managed via the Info field of the group definition within Active Directory. The field contains the CSV of UUIDs of the management playbooks for the resources within the scope of the group. As an example, if the group grants access to SSH/Server1 and MySQL/Server2 the info field would look like: `9c827fcf-53bd-403a-b3bf-406f1a27d9d8`, `0d11f906-15ea-4aa9-a665-405cd44f061f`
