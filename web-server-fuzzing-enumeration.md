# Web Server Fuzzing

## Gobuster
gobuster dir -u http://10.10.8.100 -w /usr/share/dirb/wordlists/big.txt   

## Wfuzz
wfuzz -c -z file,/usr/share/wfuzz/wordlist/general/common.txt --hc 404 http://10.10.8.100/content/FUZZ

## Nikto
nikto -h x.x.x.x
nikto -h x.x.x.x -C all
nikto -h x.x.x.x -ssl