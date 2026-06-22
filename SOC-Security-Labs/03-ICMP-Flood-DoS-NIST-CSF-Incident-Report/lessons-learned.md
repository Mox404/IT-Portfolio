# Lessons Learned

## Key Lessons

* Firewall configuration is a critical part of network availability.
* ICMP can be useful for diagnostics, but high-volume ICMP traffic can disrupt services.
* Rate limiting can reduce the impact of traffic floods without requiring all ICMP traffic to be blocked.
* Source IP verification can help reduce risk from spoofed incoming traffic.
* Network monitoring and IDS/IPS alerts can improve detection speed.
* Response plans should include service prioritization so critical services are restored first.

## What Worked In The Scenario

The incident management team took immediate containment steps by blocking incoming ICMP packets, taking non-critical services offline, and restoring critical services. These steps helped regain service availability.

## What Needed Improvement

The firewall was not configured to prevent or limit the ICMP flood before the outage occurred. The organization needed stronger preventive filtering and earlier detection of abnormal traffic patterns.

## Recommended Long-Term Improvements

* Maintain documented firewall rules and review them regularly.
* Build traffic baselines for normal ICMP behavior.
* Configure alerts for abnormal ICMP volume.
* Use IDS/IPS filtering for suspicious packet characteristics.
* Document recovery priorities for critical network services.
* Test the incident response process through tabletop exercises.

## Portfolio Reflection

This project helped me practice turning a network security incident into a structured incident report. It also helped me connect technical evidence, such as ICMP flooding and firewall configuration, to a broader security strategy using the NIST CSF functions.
