# Selected Network Hardening Tools And Methods

## Selected Methods

This assessment focuses on three hardening methods that best match the scenario vulnerabilities:

| Method | Type | Main Purpose |
| --- | --- | --- |
| Multifactor authentication | Identity and access control | Reduce risk from stolen, guessed, or shared passwords. |
| Password policy and access privileges | Account hardening | Remove default credentials and limit access based on role. |
| Firewall maintenance and port filtering | Network traffic control | Restrict unnecessary inbound and outbound traffic. |

## Multifactor Authentication

MFA requires users to verify their identity in more than one way. Examples include a password plus a one-time passcode, authenticator app approval, hardware token, or biometric verification.

### Why It Is Effective

MFA helps protect accounts even if a password is compromised. This is important in the scenario because employees share passwords and MFA is not currently used. MFA reduces the chance that password misuse immediately becomes account compromise.

### Suggested Frequency

MFA setup is usually implemented once and enforced continuously. Coverage should be reviewed regularly, especially for administrative accounts, database access, remote access, and critical applications.

## Password Policy And Access Privileges

Password policy should require unique account credentials, removal of default passwords, secure password storage practices, and clear rules against password sharing. Access privileges should follow least privilege.

### Why It Is Effective

This directly addresses the shared-password issue and the default database admin password. Unique passwords improve accountability, and least privilege limits what an attacker can access if one account is compromised.

### Suggested Frequency

Password policy should be enforced continuously. Access privilege reviews should happen on a recurring schedule and when employees join, leave, or change roles.

## Firewall Maintenance And Port Filtering

Firewall maintenance involves reviewing and updating traffic rules. Port filtering blocks or allows traffic based on approved ports and services.

### Why It Is Effective

The scenario states that firewall rules are not configured to filter traffic. Without filtering, the organization may expose unnecessary services or allow risky outbound connections. Port filtering reduces the network attack surface and supports better traffic control.

### Suggested Frequency

Firewall rules should be reviewed regularly and after major incidents, system deployments, network changes, or application changes.

## Why These Three Were Prioritized

These methods were selected because they map directly to the highest-risk issues in the scenario:

* Credential misuse risk from shared and default passwords.
* Weak authentication risk from missing MFA.
* Network exposure risk from missing firewall filtering.

Together, they improve prevention, reduce attack surface, and make unauthorized access harder.
