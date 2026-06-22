# Security Risk Assessment Report

## Lab Disclaimer

This report is based on a simulated scenario. It is written as portfolio material and does not describe a real employer incident.

## Executive Summary

A social media organization experienced a major data breach that exposed customer personal information, including names and addresses. After reviewing the scenario, four key vulnerabilities were identified:

* Employees share passwords.
* The database administrator password is still set to the default.
* Firewall rules are not configured to filter inbound and outbound traffic.
* Multifactor authentication is not used.

These weaknesses increase the risk of unauthorized access, credential misuse, lateral movement, and future data exposure. The recommended network hardening methods are multifactor authentication, stronger password and access-control practices, and firewall maintenance with port filtering.

## Part 1: Selected Hardening Tools And Methods

| Hardening method | Vulnerability addressed | Priority | Summary |
| --- | --- | --- | --- |
| Multifactor authentication | No MFA and weak credential protection | High | Requires users to verify identity with more than a password. |
| Password policy and network access privileges | Shared passwords and default database admin password | High | Reduces credential sharing, removes default credentials, and limits access based on job need. |
| Firewall maintenance and port filtering | No traffic filtering rules | High | Controls which network traffic is allowed into and out of the environment. |

## Part 2: Recommendation Explanation

### 1. Multifactor Authentication

MFA should be implemented for all administrative accounts and high-risk user accounts. MFA is effective because an attacker who steals or guesses a password still needs a second verification factor before accessing the account.

This directly addresses the organization's lack of MFA and reduces the chance that credential-based attacks lead to another breach. MFA should be configured once, enforced continuously, and reviewed regularly to ensure coverage for privileged and sensitive systems.

### 2. Password Policy And Network Access Privileges

The organization should stop password sharing, replace all default passwords, and require unique passwords for each user and administrative account. Access should also be based on job role and least privilege.

This is effective because shared passwords make it difficult to hold users accountable, and default passwords are widely known and easy to guess. Least privilege reduces damage if one account is compromised because users only have access to systems required for their role.

Password and access reviews should be performed regularly, especially when employees change roles, leave the organization, or when new systems are deployed.

### 3. Firewall Maintenance And Port Filtering

The organization should configure firewall rules to allow only approved traffic and block unnecessary inbound and outbound connections. Port filtering should be used to restrict network communication to required services.

This is effective because unfiltered traffic increases the attack surface. Firewall rules can reduce exposure by preventing unnecessary services from being reachable and by limiting suspicious outbound traffic after a compromise.

Firewall rules should be reviewed on a recurring schedule and after major network, application, or security changes.

## Risk Summary

| Vulnerability | Likelihood | Impact | Risk Level | Rationale |
| --- | --- | --- | --- | --- |
| Shared employee passwords | High | High | High | Shared credentials increase unauthorized access risk and reduce accountability. |
| Default database admin password | High | Critical | Critical | A default admin password can allow direct access to sensitive customer data. |
| No firewall filtering rules | Medium | High | High | Missing filtering allows unnecessary traffic and weakens network boundaries. |
| No MFA | High | High | High | Password-only authentication is vulnerable to guessing, reuse, phishing, and credential theft. |

## Conclusion

The organization should prioritize credential hardening and network traffic control. MFA, strong password/access-control practices, and firewall rule maintenance are practical controls that directly address the observed vulnerabilities and reduce the likelihood of another breach.
