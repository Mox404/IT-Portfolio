# Incident Report Analysis: ICMP Flood DoS

## Lab Disclaimer

This report is based on a simulated scenario. It is written as portfolio material and does not describe a real employer incident.

## Summary

A multimedia company experienced a denial-of-service attack that disrupted internal network access for approximately two hours. During the incident, network services suddenly stopped responding because the network was flooded with incoming ICMP packets. Normal internal traffic could not access required network resources.

The incident management team responded by blocking incoming ICMP packets, taking non-critical network services offline, and restoring critical network services. The cybersecurity team later determined that a malicious actor sent a high volume of ICMP ping traffic through an unconfigured firewall. This configuration weakness allowed the attacker to overwhelm network resources.

After the incident, the network security team implemented firewall ICMP rate limiting, source IP address verification, network monitoring for abnormal traffic patterns, and IDS/IPS filtering for suspicious ICMP traffic.

## Identify

| Area | Analysis |
| --- | --- |
| Attack type | Denial-of-service attack using an ICMP flood. |
| Affected systems | Internal network services and network resources used by employees. |
| Impact duration | Approximately two hours. |
| Attack source | External malicious actor sending incoming ICMP packets. |
| Vulnerability | Firewall was not configured to limit or filter incoming ICMP traffic. |
| Business impact | Employees could not access normal internal network resources during the outage. |

The main risk identified is insufficient network perimeter filtering. The unconfigured firewall allowed excessive ICMP traffic into the environment, which overwhelmed the network and interrupted availability.

## Protect

The organization should improve protective controls around firewall configuration and network availability. Recommended protection measures include:

* Maintain a firewall rule that limits the rate of incoming ICMP packets.
* Verify source IP addresses on incoming ICMP traffic to reduce spoofing risk.
* Define which ICMP traffic is required for operations and block unnecessary ICMP traffic.
* Review firewall rules regularly and after major network changes.
* Document network service dependencies so critical services can be prioritized during outages.

These controls reduce the likelihood that large volumes of ICMP traffic can reach and overwhelm internal network resources.

## Detect

The organization should improve detection by monitoring for abnormal traffic patterns. Recommended detection methods include:

* Network monitoring software to baseline normal traffic and alert on unusual spikes.
* IDS/IPS alerts for suspicious ICMP volume, frequency, or packet characteristics.
* Firewall logs to track accepted, rate-limited, and blocked ICMP traffic.
* Alerts for sudden service availability drops or network latency increases.
* Periodic review of trusted and untrusted source IP patterns.

These methods help the security team identify DoS conditions earlier and respond before network services become fully unavailable.

## Respond

For future incidents, the response plan should include:

1. Confirm the scope of the outage and affected services.
2. Review firewall, IDS/IPS, and network monitoring alerts.
3. Apply or tighten ICMP rate limits if malicious ICMP flooding is confirmed.
4. Block suspicious source traffic when feasible.
5. Temporarily take non-critical services offline to preserve capacity for critical services.
6. Communicate status to IT staff, leadership, and affected internal users.
7. Preserve relevant logs for post-incident analysis.
8. Document what was changed during containment.

The response process should focus on restoring availability while preserving evidence that helps improve future controls.

## Recover

Recovery should focus on restoring normal network operations and validating that the attack traffic is no longer disrupting services. Recommended recovery steps include:

* Restore critical network services first.
* Gradually bring non-critical services back online after traffic stabilizes.
* Validate that firewall and IDS/IPS rules are working as intended.
* Review network performance metrics after recovery.
* Document lessons learned and update the incident response plan.
* Test the updated controls through tabletop exercises or controlled simulations.

The organization should retain logs from the incident and use them to improve monitoring thresholds, firewall rules, and response procedures.

## Skills Demonstrated

* Incident report writing
* NIST CSF mapping
* DoS attack analysis
* ICMP traffic risk assessment
* Firewall hardening recommendations
* IDS/IPS and network monitoring concepts
* Response and recovery planning
