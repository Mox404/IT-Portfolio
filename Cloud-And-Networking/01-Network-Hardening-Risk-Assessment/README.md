# Network Hardening Risk Assessment

This came from a Google Cybersecurity course scenario.

The fictional company had a data breach and the main weaknesses were pretty basic but important: shared passwords, a default database admin password, no MFA, and weak firewall filtering.

## What I looked at

I matched each weakness to a control that would actually reduce the risk.

| Problem | What I would change |
| --- | --- |
| Shared passwords | unique accounts and better access control |
| Default admin password | replace it immediately and protect privileged accounts |
| No MFA | add MFA, especially for admin and sensitive access |
| Weak firewall filtering | allow only required traffic and review rules regularly |

The part I found useful was thinking about why each control matters instead of just listing security tools.

## Full writeup

[Security risk assessment](./security-risk-assessment.md)

> Course scenario only. Not a real company assessment.
