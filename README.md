# Release Information

- **Version**: 1.0.0
- **Certified**: No
- **Authored by**: Mahdi Naili (Fortinet CSE)
- **Publisher**: Community
- **Compatible Version**: FortiSOAR v7.2.0 and later

# Overview

The **Automated Employee Onboarding** Solution Pack is intended for large organizations that have a high turnover rate, with several employees leaving and joining on a daily basis. While IAM/SSO manages the majority of access, several systems (particularly legacy ones) still require local configuration to grant access to new users or disable access to those who have left.

The FortiSOAR Employee On/Off Boarding solution pack helps automate this process by provisioning access for new employees on the systems they should have access to, and disabling that access for the ones leaving the organization. The mapping of each user's access scope is done via Active Directory, where the group object holds the list of resources the members of the group can access.

Typically a user's provisioning order comes from HR, but in this simulation we assume it comes via email. The required attributes for new users are:
- Username
- Group
- Title

The following video demonstrates the functioning of this solution pack

[![Solution Pack Video Introduction](https://raw.githubusercontent.com/fortinet-fortisoar/solution-pack-employee-onboarding/release/1.0.0/docs/res/yt-thumbnail.png)](https://www.youtube.com/embed/ytVDEOY432A)

# Next Steps

| [Installation](https://github.com/fortinet-fortisoar/solution-pack-employee-onboarding/blob/release/1.0.0/docs/setup.md#installation) | [Configuration](https://github.com/fortinet-fortisoar/solution-pack-employee-onboarding/blob/release/1.0.0/docs/setup.md#configuration) | [Usage](https://github.com/fortinet-fortisoar/solution-pack-employee-onboarding/blob/release/1.0.0/docs/usage.md) | [Contents](https://github.com/fortinet-fortisoar/solution-pack-employee-onboarding/blob/release/1.0.0/docs/contents.md) |
|--------------------------------------------|----------------------------------------------|------------------------|------------------------------|
