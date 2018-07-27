# Mystery File 
 
I first cat the flagh to see that is is not a normal data file.
Using xxd I looked at the binary and noticed that there was a "XZ" in the file
which means it is probably a compressed file hidden inside the flag file.

I coppied the flag hex into my own machine to run binwalk on it to extract the hidden file

```bash
binwalk -e flag
```

Got the result:

```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
1             0x1             gzip compressed data, from Unix, last modified: 2018-01-12 15:53:42
```

And after that i catted the extracted file

```
Flag.txt0000644000000000000000000000002013226154544011164 0ustar  rootrootFLAG: hygrostat
```
