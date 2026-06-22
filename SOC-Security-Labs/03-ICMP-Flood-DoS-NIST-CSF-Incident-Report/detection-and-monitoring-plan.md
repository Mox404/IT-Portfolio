# Detection And Monitoring Plan

## Objective

Improve the organization's ability to detect ICMP flood activity and other abnormal network traffic patterns before they cause a major outage.

## Monitoring Use Cases

| Use Case | Detection Method | Why It Matters |
| --- | --- | --- |
| ICMP traffic spike | Network monitoring alert for unusual ICMP packet volume | Detects possible ICMP flood conditions early. |
| Spoofed or suspicious sources | Firewall source IP verification and logging | Helps identify traffic that should not be trusted. |
| Service availability drop | Uptime and service health monitoring | Shows whether network services are becoming unavailable. |
| Suspicious ICMP characteristics | IDS/IPS signature or behavior-based filtering | Helps filter traffic that matches known attack patterns. |
| Firewall rule changes | Configuration audit and change review | Reduces risk from unconfigured or overly permissive rules. |

## Recommended Alerts

* Incoming ICMP traffic exceeds baseline by a defined threshold.
* ICMP rate-limiting rule is triggered repeatedly.
* Critical internal services become unavailable or experience high latency.
* IDS/IPS detects flooding behavior.
* Firewall allows unexpected inbound traffic from untrusted networks.

## Log Sources

The security team should review:

* Firewall logs.
* IDS/IPS alerts.
* Network monitoring dashboards.
* Service uptime logs.
* Router or switch interface utilization metrics.
* Incident response notes and timestamps.

## Detection Improvements

The organization should establish a normal traffic baseline so the team can distinguish expected ICMP use from abnormal volume. Monitoring should include both network-level traffic indicators and user-impact indicators, such as service availability and response time.

## Analyst Notes

ICMP is not always malicious. It can support troubleshooting and diagnostic functions. The goal is not necessarily to block all ICMP traffic, but to control, rate-limit, and monitor it so legitimate use remains possible while flood conditions are detected and contained.
