# Remediation Plan

## Lab Disclaimer

This remediation plan is based on a simulated scenario and is written for portfolio documentation.

## Remediation Priorities

| Priority | Action | Reason |
| --- | --- | --- |
| 1 | Replace default database admin password | Default credentials create immediate high-impact risk. |
| 2 | Enforce MFA for admin and sensitive systems | Reduces risk from stolen, shared, or guessed passwords. |
| 3 | Stop password sharing and require unique accounts | Improves accountability and access control. |
| 4 | Configure firewall filtering rules | Reduces unnecessary network exposure. |
| 5 | Review logs and access privileges regularly | Helps detect misuse and maintain least privilege. |

## 30-60-90 Day Plan

| Timeframe | Actions |
| --- | --- |
| First 30 days | Replace default admin passwords, disable shared accounts where possible, enforce MFA for administrators, and create emergency firewall rules for critical systems. |
| 31-60 days | Expand MFA to all users, formalize password policy, review access privileges, and document approved inbound/outbound firewall rules. |
| 61-90 days | Implement recurring firewall reviews, centralize authentication and network logs, test controls, and document exceptions. |

## Implementation Cadence

| Control | Frequency |
| --- | --- |
| MFA enforcement | Continuous after rollout, with periodic coverage reviews. |
| Password policy | Continuous enforcement, reviewed after incidents or policy changes. |
| Access privilege review | Regularly and during joiner/mover/leaver events. |
| Firewall maintenance | Recurring review and after network/application changes. |
| Log review | Regular monitoring, with alerts for high-risk events. |

## Recommended Metrics

| Metric | Why It Matters |
| --- | --- |
| Percentage of users enrolled in MFA | Tracks MFA rollout completeness. |
| Number of shared accounts removed | Tracks accountability improvements. |
| Number of default credentials eliminated | Confirms high-risk credentials were replaced. |
| Firewall rules reviewed | Shows ongoing network control maintenance. |
| Failed login attempts and lockouts | Helps identify brute force or credential misuse attempts. |

## Residual Risk

Even after these controls are implemented, residual risk remains from phishing, misconfigured access, unpatched systems, and insider misuse. The organization should continue improving monitoring, patching, backups, and user security awareness.

## Recommended Next Steps

* Assign owners for identity, database, and firewall remediation tasks.
* Confirm all administrative accounts have unique credentials.
* Document firewall rules and business justification.
* Review logs for evidence of continued unauthorized access attempts.
* Reassess risk after the first 90 days of implementation.
