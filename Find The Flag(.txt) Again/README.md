# Find the flag (.txt)


First we can see that the bash does not output results from commands that regards locations such as find, grep, ls, so I wanted to
search the machine for the binaries.
```bash
cd /bin/
```

Here I saw the normal bash commands to use. 
Example use will be by calling the elf

```bash
./ls
```

After that I noticed that there was no "find" executable. We will need to search in a different way.
I used the ls command on every directory in the machine and piped it to grep to search the flag.

```bash
./ls -laR / 2>/dev/null | ./grep -i flag.txt
...Output: -rw-r--r-- 1 root root   14 Jan 10  2018 Flag.txt
```

Great! Next we need to find the location in order to cat the flag.

```bash
./ls -laR / 2>/dev/null | ./grep -B 3 -i flag.txt
...Output:/lib/x86_x64-linux-gnu/security: ...
```

Now we cat this path to get the flag: minuend

