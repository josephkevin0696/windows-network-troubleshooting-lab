# Windows Network Troubleshooting Lab

A hands-on Windows command-line troubleshooting exercise using routing, ARP, ICMP, and traceroute information to reason through local and remote network connectivity.

> **Portfolio note:** Local username paths, MAC addresses, and identifying external route details were removed from the screenshots before publication. Private RFC1918 addresses are retained because they are useful to explain the lab.

## Commands practiced

| Command | What it helps verify |
|---|---|
| ipconfig /all | Interface configuration, IP addressing, subnet mask, default gateway, DNS, DHCP |
| route print -4 | IPv4 routing table and default route |
| arp -a | Local IP-to-MAC neighbor resolution |
| ping <gateway> | Layer 3 reachability to the local gateway |
| tracert 8.8.8.8 | Hop-by-hop Layer 3 path toward a remote destination |

## Lab observations

- The active host used the private IPv4 address 10.0.0.51/24.
- The default gateway was 10.0.0.1.
- The IPv4 routing table contained a default route through the gateway.
- ARP showed a resolved neighbor entry for the gateway.
- A ping to 10.0.0.1 succeeded with no packet loss in the captured test.
- A traceroute to 8.8.8.8 progressed beyond the local gateway, demonstrating a routed path toward the Internet.
- A failed test to another address was useful for comparing reachable vs. non-reachable targets.

## Evidence

### Routing table, ARP, and local gateway testing
![Windows route table and ARP evidence](evidence/01-route-arp-and-gateway-test.jpg)

### Ping and traceroute testing
![Windows ping and traceroute evidence](evidence/02-ping-and-traceroute.jpg)

## Troubleshooting method

1. Check interface state
2. Verify IP address and subnet mask
3. Verify default gateway
4. Inspect the routing table
5. Inspect ARP / neighbor resolution
6. Ping the local gateway
7. Test a remote destination
8. Use traceroute to identify where the path changes or fails

## Skills demonstrated

Windows · TCP/IP · IPv4 · Subnetting · Routing · ARP · ICMP · Ping · Traceroute · Layered Troubleshooting

## Scope and limitations

This is a troubleshooting practice lab, not evidence of managing an enterprise network. The goal is to demonstrate a repeatable diagnostic thought process and familiarity with core Windows networking tools.
