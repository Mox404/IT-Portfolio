# DNS and ICMP Traffic Analysis

This was a Google Cybersecurity traffic analysis exercise.

The user report was basically "the website is not working." The packet data showed that the problem happened earlier than the website itself.

The client kept sending DNS A record queries to the DNS server over UDP port 53. The server kept replying with ICMP messages saying UDP port 53 was unreachable.

## What that told me

The client could not complete DNS resolution, so it could not get as far as a normal web connection.

Possible causes included the DNS service being down, UDP 53 being blocked, the service not listening correctly, or the client using the wrong DNS server.

That is the main thing I took from this one: do not jump straight to the browser or web server when name resolution is already failing.

## Files

[Tcpdump breakdown](./tcpdump-analysis.md)

[Sanitized traffic sample](./sanitized-tcpdump-log.txt)

> Guided course scenario, not a production incident.
