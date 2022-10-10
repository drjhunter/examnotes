# Network Connectivity

## RDP
`xfreerdp /v:10.10.37.245 /u:pwnd /p:SimplePass123`

## SMBMap for scanning
Downloaded smbmap from github repo https://github.com/ShawnDEvans/smbmap
`python3 smbmap-master/smbmap.py -H $IP -u any`

[+] IP: 10.10.220.97:445	Name: ip-10-10-220-97.eu-west-1.compute.internal	Status: Guest session   	
        Disk                                                  	Permissions	Comment
	----                                                  	-----------	-------
	ADMIN$                                            	NO ACCESS	Remote Admin
	C$                                                	NO ACCESS	Default share
	IPC$                                              	READ ONLY	Remote IPC
	nt4wrksv                                          	READ, WRITE	

## Enumerate for SMB shares
`nmap -p 445 --script=smb-enum-shares.nse,smb-enum-users.nse 10.10.62.89`

## SMBClient for connecting
`smbclient \\$IP\nt4wrksv` # complains about not enough \
`smbclient \\\\$IP\\nt4wrksv` # this works, asked for password, just pressed <enter>

## HTTP
Post
`curl -X POST -d 'namePeople=daedalus' 10.10.74.142/api/people/search` 

## RPC port 111
`nmap -p 111 --script=nfs-ls,nfs-statfs,nfs-showmount 10.10.62.89`

## Get FTP banner
`nc x.x.x.x 21`
