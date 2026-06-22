# Portfolio Summary

## Project

DNS and ICMP Traffic Analysis: UDP Port 53 Unreachable

## Short Description

Analyzed sanitized tcpdump output from a simulated cybersecurity lab to investigate why users could not access a website. The traffic showed repeated DNS A record queries to a DNS server followed by ICMP `udp port 53 unreachable` errors, indicating that DNS resolution was failing.

## What I Analyzed

* DNS queries for `yummyrecipesforme.com`
* Client-to-DNS-server communication over UDP port 53
* ICMP port unreachable responses
* The relationship between DNS failure and website access failure

## Key Finding

The client could not resolve the website domain because the DNS server returned ICMP errors showing UDP port 53 was unreachable. The evidence suggests a DNS service availability, firewall, listener, or configuration issue.

## What I Recommended

* Verify DNS service status.
* Confirm that DNS is listening on UDP port 53.
* Review firewall and ACL rules.
* Check client DNS configuration.
* Review DNS server logs.
* Validate DNS resolution after remediation.

## Skills Demonstrated

* Network traffic analysis
* DNS troubleshooting
* ICMP error interpretation
* UDP port/service identification
* Incident documentation
* TCP/IP model understanding

## Interview Talking Points

* I can explain how DNS resolution happens before a browser can connect to a website.
* I can interpret tcpdump output and identify source IP, destination IP, protocol, port, and error messages.
* I understand how ICMP errors can help narrow down network and service availability issues.
* I document findings carefully and separate confirmed evidence from hypotheses.

## Disclaimer

This is a scenario-based portfolio project. It is included to demonstrate analysis and documentation skills, not to claim real-world incident response ownership.
