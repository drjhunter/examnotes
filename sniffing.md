# Sniffing

## MAC Flooding
Show that all machines on subnet receive same packets by running Wireshark on all hosts
`macof -i eth0 -d t.t.t.t`

## DHCP Starvation
Flood DHCP with bogus DISCOVER packets until the DHCP server exhauts its supply of IP addresses.
Results in network DOS, alernatively attacker can supply their owh DHCP server -> MITM attack
`yersinia -I`

## ARP Poisoning
Attack box running e.g. arpspoof or Cain and Abel, interferes with ARP traffic until the victim ARP cache is corrupted. Gateway's IP address now maps to attacher's MAC, so all packets will be sent there first. If the attackbox runs a proxy tool like Ettercap, victim will be unaware and MiTM achieved. This is the foundation for DNS poisoning.
Windows GUI Cain and Abel
`arpspoof -i eth0 -t g.g.g.g t.t.t.t` - g for gateway, t for target

## MAC Spoofing
Allows attacker to take over the identity of another host on the network
Windows GUI TMAC and SMAC

## Network Analysis Tools
Windows GUI Capsa,OmniPeek, Steel Central

## Detect ARP Poisoning
`nmap --script sniffer-detect x.x.x.x` - CIDR range or single IP of suspected attack box
Windows GUI XARP
HPing to generate clean traffic, plus Wireshark  with special configuration to detect poisoned traffic:
- Edit -> Preferences -> Protocol -> ARP
- Analyse -> Export Info


