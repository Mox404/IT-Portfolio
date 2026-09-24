# Tcpdump Analysis

This was the packet sample from the Google Cybersecurity DNS exercise.

## What I saw

The client kept asking the DNS server for an A record for `yummyrecipesforme.com`.

Example query:

```text
13:24:32.192571 IP 192.51.100.15.52444 > 203.0.113.2.domain: 35084+ A? yummyrecipesforme.com. (24)
```

The important parts are:

| Field | What it tells me |
| --- | --- |
| `192.51.100.15.52444` | client IP and temporary source port |
| `203.0.113.2.domain` | destination DNS server using the DNS service |
| `A?` | request for an IPv4 address |
| `yummyrecipesforme.com` | name the client is trying to resolve |

Instead of a normal DNS answer, the server returned:

```text
13:24:36.098564 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2 udp port 53 unreachable length 254
```

The useful part there is `udp port 53 unreachable`.

## Why that matters

The same pattern happened more than once. This was not just one random dropped packet.

The client was failing at DNS resolution, so there is no evidence in this sample that it ever got as far as connecting to the web server.

Possible causes I would check are:

* DNS service stopped or unhealthy
* UDP port 53 blocked
* DNS not listening on UDP 53
* wrong DNS configuration
* client pointed at the wrong DNS server

The packet capture narrows the problem down, but it does not prove the exact root cause by itself. I would still need service status, DNS configuration, and firewall or server logs to confirm it.

> Sanitized course traffic, not a production capture.
