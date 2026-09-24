# NIST CSF Action Plan

I used the NIST Cybersecurity Framework to organize what should happen before, during, and after the ICMP flood scenario.

| Function | What I would focus on |
| --- | --- |
| Identify | know the critical services, firewall setup, dependencies, and business impact |
| Protect | filter or rate limit unnecessary ICMP traffic and keep firewall rules reviewed |
| Detect | watch ICMP volume, latency, service availability, firewall events, and IDS or IPS alerts |
| Respond | contain the traffic, preserve logs, protect critical services, and keep people updated |
| Recover | restore the important services first, verify the controls, then bring the rest back |

## Identify

I would make sure the company knows which internal services matter most and what network devices sit in front of them.

The original scenario showed why firewall configuration and network capacity both need to be part of the risk review.

## Protect

I would use sensible ICMP filtering and rate limits rather than just allowing everything.

Firewall rules should also be documented so someone can tell why a rule exists later.

## Detect

The useful signs would be things like:

* a sudden jump in ICMP traffic
* higher latency or packet loss
* service availability dropping
* firewall rate limit events
* IDS or IPS alerts

## Respond

If it happens again, I would first confirm the traffic pattern and affected services, then tighten filtering, keep the important services available if possible, and save the logs for later review.

## Recover

After the flood is under control, I would restore the most important services first and check that users can reach them normally.

Then I would bring the rest back, review the monitoring data, and update the response steps based on what actually happened.

> This is a course exercise based on a fictional incident.
