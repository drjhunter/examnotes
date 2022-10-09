# Evading IDS, Firewalls and Honeypots

## Intrusion detection using Snort
`snort` - to initialise, then <ctrl> C
`snort -W` - lists Ethernet drivers, all disabled by default. Note the index number.
`snort -dev -i 1` - enables Driver 1 and runs in packet dump mode

## Evade firewall using nmap zombies - to achieve useful nmap scan of ports
`nmap -sI z.z.z.z t.t.t.t` - Zombie scan - useful when the attackbox IP is blocked by firewall

## Evade firewall using HTTP/FTP tunnelling - to achieve a connection that would otherwise be blocked
Run HTTPPort on the client side of the firewall and HTTPHost on the server side.Establishes an HTTP tunnel.
`ftp 127.0.0.1` - FTP Client -> HTTPPort -> HTTPHost -> FTP Server


