| [Home](https://github.com/fortinet-fortisoar/solution-pack-employee-onboarding/blob/release/1.0.0/README.md) |
|--------------------------------------------|

# Usage

Refer to [Simulate Scenario documentation](https://github.com/fortinet-fortisoar/solution-pack-soc-simulator/blob/develop/docs/solution-pack-guide.md) to understand how to simulate and reset scenarios.

To understand the process FortiSOAR follows to respond to **Employee Onboarding**, we have included a scenario &mdash; **Employee Onboarding** with this solution pack. Refer to the section [Employee Onboarding](#employee-onboarding) to understand how this solution pack automation addresses your needs.

## Simulation mode (Fake mock data)
    
*    Edit global variables: EOF_SYS_User and EOF_DB_User and populate them with names of your choice.
*    Browse to Simulations, select the scenario and click Run scenario.
*    Four Alerts will be created at 30 seconds interval:
        - System user Onboarding
        - System user Offboarding
        - DBA user Onboarding
        - DBA user Offboarding
*    For Each alert track the associated playbooks to see what services are being provisioned based on the group defined in the user provisioning email request

## Live mode (Real data)
*   To Onboard a user send an email to your FortiSOAR mailbox with:
    - Subject: user ... onboarding
    - body:
        - Username: ad_username_to_create
        - Group: ad_group
        - Title: job_title
*   To Offboard a user send an email to your FortiSOAR mailbox with:
    - Subject: user ... offboarding
    - body:
        - Username: ad_username_to_create
        - Group: ad_group

Make sure the groups your users belong to have the appropriate management playbooks UUIDs in their info attribute in CSV format