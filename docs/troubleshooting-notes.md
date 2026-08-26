# Troubleshooting Notes

## Layered reasoning

### 1. Local configuration
Start by confirming the host has a valid address, subnet mask, gateway, and DNS configuration.

### 2. Route selection
route print -4 shows where Windows will send traffic. The default route is used when no more-specific route matches.

### 3. Neighbor resolution
arp -a shows local IPv4-to-MAC mappings. If the default gateway cannot be resolved on the local segment, remote communication cannot proceed normally.

### 4. Local gateway test
A successful ping to the default gateway confirms that the host can reach the router at Layer 3.

### 5. Remote path test
tracert helps identify whether packets leave the local network and how far they progress toward a remote destination.

## Evidence handling
The public screenshots deliberately retain private lab IPv4 addresses but remove local usernames, MAC addresses, public IPv6 data, and external route details that are unnecessary for a portfolio reviewer.
