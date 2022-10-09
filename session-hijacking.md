# Session Hijacking

## HTTP - ZAP Proxy

## HTTP - Bettercap
`bettercap -iface eth0`
net.probe = on - probe every IP in the subnet
net.recon = on - tracks response to probes
net.sniff.regexp = '.*password=.+' - the regex to look for
http.proxy.sslstrip = true - for inspecting https

# Detect Session Hijacking
## Wireshark
Attackbox originates broadcast requests to all IPs on subnet.
Additionally, able to observer proxy behaviour (forwarding) victim -> attacker -> gateway -> attacker -> victim.

