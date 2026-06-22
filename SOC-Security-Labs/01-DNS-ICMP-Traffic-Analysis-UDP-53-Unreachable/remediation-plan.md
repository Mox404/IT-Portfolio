# Remediation Plan

## Lab Disclaimer

This remediation plan is written for a scenario-based portfolio project. These are recommended next steps based on traffic analysis, not actions I performed on a real production system.

## Objective

Restore DNS resolution for users attempting to access `www.yummyrecipesforme.com` by confirming that DNS service on UDP port 53 is available, correctly configured, and reachable from the client network.

## Priority

This should be treated as a high-priority service availability issue because users cannot reach the website when DNS resolution fails.

## Recommended Investigation Steps

| Step | Action | Reason |
| --- | --- | --- |
| 1 | Confirm DNS service status on `203.0.113.2`. | Determines whether the DNS service is running. |
| 2 | Verify the DNS service is listening on UDP port 53. | The tcpdump error specifically reports UDP port 53 unreachable. |
| 3 | Review host firewall rules on the DNS server. | Local firewall rules may block DNS requests. |
| 4 | Review network firewall or ACL rules. | Network controls may block UDP 53 between client and server. |
| 5 | Test DNS resolution from another client. | Confirms whether the issue affects one client or a wider user group. |
| 6 | Confirm client DNS configuration. | The client may be using the wrong DNS server. |
| 7 | Review DNS server logs. | Logs may show service failures, misconfiguration, or refused requests. |

## Remediation Recommendations

* Restart or restore the DNS service if it is stopped.
* Correct DNS service configuration if the service is not bound to the expected interface or port.
* Allow UDP port 53 through approved firewall rules if it is being blocked.
* Validate that clients are configured to use the correct DNS resolver.
* Add monitoring for DNS service availability and port reachability.
* Document the final root cause once server-side logs and configuration are reviewed.

## Validation Steps

After remediation, validation should include:

* DNS lookup for `yummyrecipesforme.com` returns an IP address.
* No new ICMP `udp port 53 unreachable` errors appear during testing.
* Browser access to `www.yummyrecipesforme.com` works as expected.
* DNS server logs show successful query handling.
* Monitoring confirms DNS service availability.

## Communication Notes

For stakeholders, the issue can be summarized as:

Users could not access the website because DNS resolution was unavailable. Traffic analysis showed that DNS queries to UDP port 53 were answered with ICMP port unreachable errors. The recommended next steps are to verify DNS service status, firewall rules, and DNS server configuration.

## Lessons Learned

* DNS availability is a dependency for website access.
* A port unreachable ICMP error can quickly narrow troubleshooting to service availability, listening state, or filtering.
* Tcpdump evidence should be combined with server logs and configuration checks before declaring a final root cause.
* Incident documentation should clearly distinguish between observed evidence and hypotheses.
