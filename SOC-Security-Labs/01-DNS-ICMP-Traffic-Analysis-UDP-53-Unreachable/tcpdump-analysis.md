# Tcpdump Analysis

## Lab Disclaimer

This analysis uses sanitized tcpdump output from a scenario-based portfolio project. The IP addresses and domain are used only for portfolio documentation.

## What The Tcpdump Output Shows

The traffic sample shows a client attempting to resolve `yummyrecipesforme.com` through DNS. The client sends DNS A record queries to a DNS server over UDP port 53. Instead of a successful DNS response, the DNS server returns ICMP errors stating that UDP port 53 is unreachable.

## Field Breakdown

Example query:

```text
13:24:32.192571 IP 192.51.100.15.52444 > 203.0.113.2.domain: 35084+ A? yummyrecipesforme.com. (24)
```

| Field | Meaning |
| --- | --- |
| `13:24:32.192571` | Timestamp showing when the packet was captured. |
| `IP` | Indicates the packet used Internet Protocol. |
| `192.51.100.15.52444` | Source client IP and source port. The client used ephemeral source port `52444`. |
| `>` | Direction of traffic from source to destination. |
| `203.0.113.2.domain` | Destination DNS server. `domain` means DNS service, normally UDP port 53. |
| `35084+` | DNS transaction ID and query flags. |
| `A?` | DNS A record query, asking for the IPv4 address of a domain. |
| `yummyrecipesforme.com.` | Domain name being resolved. |
| `(24)` | Packet payload length shown by tcpdump. |

Example error:

```text
13:24:36.098564 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2 udp port 53 unreachable length 254
```

| Field | Meaning |
| --- | --- |
| `13:24:36.098564` | Timestamp showing when the error packet was captured. |
| `203.0.113.2` | Source IP of the ICMP error response. |
| `192.51.100.15` | Destination client IP receiving the error. |
| `ICMP` | Internet Control Message Protocol, used for network error messages. |
| `udp port 53 unreachable` | The DNS service on UDP port 53 could not be reached. |
| `length 254` | Size of the ICMP packet reported by tcpdump. |

## Clean Traffic Summary

| Timestamp | Direction | Protocol | Interpretation |
| --- | --- | --- | --- |
| 13:24:32.192571 | Client to DNS server | DNS/UDP | DNS A record query for `yummyrecipesforme.com`. |
| 13:24:36.098564 | DNS server to client | ICMP | UDP port 53 unreachable error. |
| 13:26:32.192571 | Client to DNS server | DNS/UDP | Repeated DNS A record query. |
| 13:27:15.934126 | DNS server to client | ICMP | UDP port 53 unreachable error repeated. |
| 13:28:32.192571 | Client to DNS server | DNS/UDP | Third observed DNS A record query. |
| 13:28:50.022967 | DNS server to client | ICMP | UDP port 53 unreachable error repeated again. |

## Interpretation

The client sent multiple DNS lookup attempts over several minutes. Each attempt was followed by an ICMP error from the DNS server. This pattern indicates that the issue was not a single dropped packet. The repeated failures point to a persistent DNS service reachability problem.

The important detail is that the failure happened during DNS resolution. There is no evidence in this sample that the client reached the web server. The browser could not move forward because it could not translate the domain name into an IP address.

## Root Cause Hypotheses

Based on the available traffic, the most likely causes are:

* DNS service was down on `203.0.113.2`.
* DNS was running but not listening on UDP port 53.
* A firewall blocked UDP port 53 traffic.
* DNS service configuration was incorrect.
* The client was pointed to the wrong DNS server.

## Analyst Notes

The tcpdump sample supports a DNS availability or reachability issue. More evidence would be needed to confirm the final root cause, such as DNS server logs, service status checks, firewall logs, and configuration review.
