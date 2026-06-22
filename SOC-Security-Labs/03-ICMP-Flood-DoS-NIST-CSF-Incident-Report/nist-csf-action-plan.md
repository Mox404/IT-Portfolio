# NIST CSF Action Plan

## Purpose

This action plan maps the simulated ICMP flood DoS incident to the five NIST CSF functions: Identify, Protect, Detect, Respond, and Recover.

## NIST CSF Mapping

| Function | Goal | Recommended Actions |
| --- | --- | --- |
| Identify | Understand affected assets, risks, and dependencies. | Inventory critical network services, review firewall configuration, identify systems affected by ICMP flooding, and document business impact. |
| Protect | Reduce the chance or impact of future attacks. | Apply ICMP rate limiting, source IP verification, firewall rule reviews, and IDS/IPS filtering for suspicious ICMP patterns. |
| Detect | Identify abnormal activity quickly. | Monitor ICMP volume, firewall events, service availability, network latency, and IDS/IPS alerts. |
| Respond | Contain and analyze future events. | Block suspicious traffic, preserve logs, prioritize critical services, communicate status, and document containment actions. |
| Recover | Restore normal operations and improve resilience. | Restore critical services, validate controls, return non-critical services online, review lessons learned, and update procedures. |

## Identify: Risk And Asset Review

The organization should maintain an inventory of:

* Critical internal network services.
* Firewall and perimeter network devices.
* Network monitoring tools.
* IDS/IPS systems.
* Business teams dependent on internal network access.

The incident showed that network availability is a critical business requirement. Future risk reviews should include firewall configuration audits and traffic handling capacity.

## Protect: Preventive Controls

Protective controls should focus on reducing exposure to unnecessary ICMP traffic and limiting the effect of traffic floods:

* Configure ICMP rate limits.
* Verify source IP addresses where possible.
* Block unnecessary inbound ICMP traffic.
* Keep firewall rules documented and reviewed.
* Use IDS/IPS filtering for suspicious traffic characteristics.

## Detect: Monitoring Improvements

Detection should focus on early signs of traffic flooding:

* Unusual increase in incoming ICMP packets.
* Increased latency or packet loss.
* Sudden drop in service availability.
* Firewall rule hits or rate-limit events.
* IDS/IPS alerts related to flooding patterns.

## Respond: Containment Workflow

If a similar incident occurs, the team should:

* Validate the traffic pattern.
* Confirm which services are affected.
* Tighten filtering or rate limits.
* Isolate or deprioritize non-critical services.
* Keep stakeholders updated.
* Preserve logs for investigation.

## Recover: Restoration Workflow

After containment, the team should:

* Restore critical network services first.
* Confirm normal internal traffic can access network resources.
* Bring non-critical services back online in stages.
* Review monitoring data for recurring abnormal traffic.
* Update firewall, IDS/IPS, and response playbook documentation.
