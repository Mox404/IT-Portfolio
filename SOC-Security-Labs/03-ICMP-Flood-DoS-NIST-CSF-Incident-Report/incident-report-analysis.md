# Incident Analysis: ICMP Flood DoS

This is based on the fictional Google Cybersecurity course scenario.

The company lost access to internal network services for about two hours because a large amount of ICMP traffic was allowed through a badly configured firewall.

## What happened

The traffic flood used up network capacity and normal users could not reach the services they needed.

The response team blocked incoming ICMP traffic, took noncritical services offline, and brought the important services back first.

The main weakness was the firewall configuration. It was not limiting or filtering the ICMP traffic properly.

## What I would change

For protection:

* rate limit ICMP where it makes sense
* block unnecessary ICMP traffic
* review firewall rules after major changes
* keep track of which services are actually critical

For detection:

* monitor traffic volume and latency
* alert on unusual ICMP spikes
* use firewall and IDS or IPS logs
* watch for sudden service availability problems

For response:

1. confirm what is affected
2. check firewall and monitoring data
3. tighten filtering or rate limits
4. protect the most important services first
5. keep the relevant logs
6. document what was changed

For recovery:

1. restore critical services first
2. bring the rest back once traffic is stable
3. check that the new firewall and monitoring rules are working
4. review what happened and update the response steps

The main lesson for me was that fixing the traffic flood is only one part of the job. You still need monitoring, a response plan, and a way to restore services in the right order.

> Course scenario only. Not a real outage I handled.
