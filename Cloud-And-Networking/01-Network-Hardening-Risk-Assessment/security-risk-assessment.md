# Security Risk Assessment

This is based on the fictional Google Cybersecurity course scenario.

A social media company had a breach that exposed customer information. The scenario pointed to four obvious weaknesses:

* employees shared passwords
* the database admin password was still the default
* firewall filtering was not properly set up
* MFA was not being used

## What I would fix first

| Problem | Why it matters | What I would do |
| --- | --- | --- |
| Shared passwords | weak accountability and easier credential misuse | give users unique accounts and review access |
| Default database admin password | gives an attacker an easy path to privileged access | replace it immediately and protect admin access |
| No MFA | a stolen password can be enough to take over an account | require MFA, starting with admin and sensitive accounts |
| Weak firewall filtering | unnecessary traffic and services stay exposed | allow only required traffic and review rules regularly |

## Why I picked those controls

MFA helps when a password is stolen or guessed because the attacker still needs another factor.

Unique accounts and least privilege make activity easier to trace and limit what one compromised account can reach.

Firewall filtering reduces the number of services and traffic paths that are exposed for no reason.

## Risk view

| Weakness | Likelihood | Impact | My rating |
| --- | --- | --- | --- |
| Shared employee passwords | High | High | High |
| Default database admin password | High | Critical | Critical |
| Weak firewall filtering | Medium | High | High |
| No MFA | High | High | High |

## What I would do next

I would start with the default admin credential and MFA because those are direct account takeover risks. After that I would clean up shared access and firewall rules, then keep reviewing access and logs instead of treating it as a one time fix.

> Course scenario only. This is not a real breach assessment.
