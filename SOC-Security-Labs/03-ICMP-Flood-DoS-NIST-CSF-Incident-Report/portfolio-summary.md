# Portfolio Summary

## Project

ICMP Flood DoS Incident Report Using the NIST CSF

## Short Description

Created a simulated incident report for a denial-of-service attack where an unconfigured firewall allowed a flood of incoming ICMP packets to disrupt internal network services for approximately two hours.

## What I Analyzed

* ICMP flood denial-of-service behavior.
* Firewall configuration weakness.
* Internal network availability impact.
* Incident response actions taken during the outage.
* Post-incident controls including rate limiting, source IP verification, network monitoring, and IDS/IPS filtering.

## Framework Used

The report is organized using the NIST CSF functions:

* Identify
* Protect
* Detect
* Respond
* Recover

## Key Finding

The incident was caused by excessive incoming ICMP traffic passing through an unconfigured firewall. This overwhelmed internal network services and prevented normal traffic from accessing network resources.

## Recommended Improvements

* Maintain ICMP rate-limiting firewall rules.
* Verify source IP addresses for incoming ICMP traffic where possible.
* Use network monitoring to detect abnormal traffic patterns.
* Deploy IDS/IPS filtering for suspicious ICMP characteristics.
* Document response and recovery procedures for future DoS incidents.

## Skills Demonstrated

* Incident report writing
* NIST CSF mapping
* DoS attack analysis
* ICMP traffic risk assessment
* Firewall hardening recommendations
* IDS/IPS and network monitoring concepts
* Response and recovery planning

## Interview Talking Points

* I can apply the NIST CSF to structure an incident report.
* I can explain how an ICMP flood can affect network availability.
* I can distinguish between containment, detection, response, and recovery steps.
* I can connect technical controls to business continuity and service availability.

## Disclaimer

This is a scenario-based portfolio project. It is included to demonstrate analysis and documentation skills, not to claim real-world incident response ownership.
