# Glossary

## DNS

Domain Name System. DNS translates domain names, such as `www.yummyrecipesforme.com`, into IP addresses that computers can use to connect to services.

## DNS A Record

An A record maps a domain name to an IPv4 address. In the tcpdump sample, `A? yummyrecipesforme.com.` means the client asked for the IPv4 address of that domain.

## UDP

User Datagram Protocol. UDP is a connectionless transport protocol. DNS commonly uses UDP because DNS queries are usually small and fast.

## UDP Port 53

The standard UDP port for DNS queries. If UDP port 53 is unreachable, clients may not be able to resolve domain names through that DNS server.

## ICMP

Internet Control Message Protocol. ICMP is used to send network control and error messages. In this lab, ICMP was used to report that UDP port 53 was unreachable.

## Port Unreachable

An error message indicating that the destination host or network path could not deliver traffic to the requested port. In this project, `udp port 53 unreachable` indicates the DNS service was not reachable on UDP port 53.

## Source IP

The IP address that sends a packet. In the DNS query, the source IP is `192.51.100.15`, the client.

## Destination IP

The IP address that receives a packet. In the DNS query, the destination IP is `203.0.113.2`, the DNS server.

## Source Port

The port selected by the sending device. In the sample, the client used source port `52444`, which is an ephemeral port.

## Destination Service

The service the client is trying to reach. In the sample, `domain` represents DNS service on port 53.

## Tcpdump

A command-line packet capture tool used to inspect network traffic. Tcpdump can show timestamps, IP addresses, ports, protocols, DNS queries, and error messages.

## TCP/IP Model

A layered model used to understand network communication. This project touches multiple layers: IP addressing at the internet layer, UDP at the transport layer, DNS at the application layer, and ICMP for network error reporting.
