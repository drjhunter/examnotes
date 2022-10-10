# Linux

## List files, including hidden
`ls -lah`

## Find
`Find / -type f -name wordlist 2>/dev/null`
`find / -writable 2>/dev/null | cut -d "/" -f 2,3 | grep -v proc | sort -u ` - find writable folders
`find / -type f -perm -04000 -ls 2>/dev/null` - find files with suid

## Inspect a binary file for readable strings
`strings executablefile`

## Edit environment variable
`Export PATH=/tmp:$PATH`

## Grep
`ps -ef | grep "sh$"` - lines ending in sh
`grep -e admin /usr/share/wordlists/rockyou.txt -n -m 10` - n for linenumbers, e for searchpattern
`sudo grep -x '.\{4,6\}' /usr/share/wordlists/rockyou.txt > NEWrockyou.txt` - filtering wordlists to get words of a certain length (4 to 6 letters in this example)

## Sed
Copy lines 45000 - 50000 from rockyou into a new file
`sed -n '45000,50000p' /usr/share/wordlists/rockyou.txt >/usr/share/wordlists/shortrockyou.txt`

