# Incident Report: DNS and ICMP Traffic Analysis

## Lab Disclaimer

This report is based on a simulated network traffic analysis scenario. It is written as a portfolio report and does not describe a real employer incident.

## Executive Summary

Users were unable to access `www.yummyrecipesforme.com`. The browser attempted to resolve the domain name through DNS, but the DNS requests did not complete successfully.

The sanitized tcpdump output showed repeated DNS A record queries from client `192.51.100.15` to DNS server `203.0.113.2` using UDP port 53. The DNS server returned ICMP errors stating that UDP port 53 was unreachable. Based on this evidence, the most likely issue was that the DNS service on the server was unavailable, blocked, misconfigured, or not listening on UDP port 53.

I analyzed the provided traffic and documented recommended next steps. I did not resolve or remediate a live incident.

## Incident Details

| Field | Value |
| --- | --- |
| Affected user activity | Website access |
| Affected domain | `www.yummyrecipesforme.com` |
| Client IP | `192.51.100.15` |
| DNS server IP | `203.0.113.2` |
| Affected service | DNS |
| Affected port | UDP port 53 |
| Protocols involved | DNS, UDP, ICMP |
| Observed time window | Approximately 13:24 to 13:28 |
| Primary error | `udp port 53 unreachable` |

## Traffic Summary

| Time | Source | Destination | Protocol | Summary |
| --- | --- | --- | --- | --- |
| 13:24:32 | `192.51.100.15:52444` | `203.0.113.2:53` | DNS over UDP | Client queried A record for `yummyrecipesforme.com`. |
| 13:24:36 | `203.0.113.2` | `192.51.100.15` | ICMP | DNS server returned UDP port 53 unreachable. |
| 13:26:32 | `192.51.100.15:52444` | `203.0.113.2:53` | DNS over UDP | Client retried the A record query. |
| 13:27:15 | `203.0.113.2` | `192.51.100.15` | ICMP | DNS server again reported UDP port 53 unreachable. |
| 13:28:32 | `192.51.100.15:52444` | `203.0.113.2:53` | DNS over UDP | Client made another DNS query attempt. |
| 13:28:50 | `203.0.113.2` | `192.51.100.15` | ICMP | DNS server again reported UDP port 53 unreachable. |

## Analysis

The browser needed an IP address before it could connect to the website. To get that IP address, the client sent DNS A record queries for `yummyrecipesforme.com` to the configured DNS server.

The DNS queries used UDP port 53, which is the standard port for most DNS lookups. Instead of returning a DNS answer, the server responded with ICMP errors indicating that UDP port 53 was unreachable. This means the client could not receive a valid DNS response, so the domain could not be resolved to an IP address.

Because DNS resolution failed, users could not reach the website through the browser.

## Root Cause Hypotheses

The tcpdump sample does not prove one final root cause, but it supports the following likely causes:

* DNS service on `203.0.113.2` was stopped or unavailable.
* DNS service was not listening on UDP port 53.
* A firewall or network access control rule blocked UDP port 53.
* DNS server configuration was incorrect.
* The client was configured to use the wrong DNS server.

## Business Impact

The business impact was loss of website access for users. Even if the web server itself was available, users could not access the site because the browser could not resolve the domain name to an IP address.

## Recommended Next Steps

* Check whether the DNS service is running on `203.0.113.2`.
* Verify that the DNS server is listening on UDP port 53.
* Review firewall rules between the client network and DNS server.
* Test DNS resolution using a known-good DNS client or command-line lookup tool.
* Confirm that clients are configured to use the correct DNS server.
* Review DNS server logs for service errors, dropped requests, or configuration issues.

## Skills Demonstrated

* Network traffic analysis
* DNS troubleshooting
* ICMP error interpretation
* UDP port/service identification
* Incident documentation
* TCP/IP model understanding
