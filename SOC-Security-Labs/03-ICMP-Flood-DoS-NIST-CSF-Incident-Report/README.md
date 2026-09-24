# ICMP Flood DoS with NIST CSF

This was a Google Cybersecurity incident response exercise.

The fictional company lost network availability for about two hours after a large amount of ICMP traffic passed through a poorly configured firewall.

## What I worked through

The immediate response was about restoring service and reducing the flood. The longer term part was figuring out what should change so the same thing was easier to prevent, detect, and handle next time.

I mapped that work to the NIST CSF functions:

| Function | What it meant in this case |
| --- | --- |
| Identify | know the affected services and the firewall weakness |
| Protect | rate limit or filter unnecessary ICMP traffic |
| Detect | watch for unusual traffic spikes and IDS or IPS alerts |
| Respond | contain the traffic, keep logs, and protect critical services |
| Recover | restore services and check that the new controls work |

## Files

[Incident analysis](./incident-report-analysis.md)

[NIST CSF action plan](./nist-csf-action-plan.md)

> Guided course scenario, not a real production outage.
