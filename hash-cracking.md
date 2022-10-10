# Hash Cracking

## Hashid to find hash format
`hashid`

## Hashcat formats and algorithms
https://hashcat.net/wiki/doku.php?id=example_hashes



## count the lines in a text file
`Wc -l <filename>`

## John
Ask John which hash formats it supports
`John --list=formats`

`john --format=bcrypt hash.txt --wordlist=NEWrockyou.txt`

Ask hashcat if it supports a format
`Hashcat --help | grep <hashformatname>`

3200 = bcrypt
`hashcat -m 3200 hash.txt NEWrockyou.txt`
`hashcat -m3200 -a0 --force hashes.txt --wordlist /usr/share/wordlists/shortrockyou.txt`

## salt explanation: https://crackstation.net/hashing-security.htm

HMAC-SHA512 with salt using John: put the hash in a text file $<format>$<salt>$<hash>
Hash: $6$aReallyHardSalt$6WKUTqzq.UQQmrm0p/T7MPpMbGNnzXPMAXi4bJMl9be.cfi3/qxIf.hsGpS41BqMhSrHVXgMpdjS6xeKZAs02.
`John tocrack.txt --format=sha512crypt --wordlist=shortrock.txt`

HMAC-SHA512 with salt using Hashcat
`Hashcat -m 1800 hash.txt words.txt`