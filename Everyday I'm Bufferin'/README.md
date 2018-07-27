# Everyday I'm Bufferin'
 
This challenge is about executing buffer overflow in order to retrieve the flag
At first we run the program and see that it copy and pastes our input.
Lets dissassemble this program to understand better.

```bash
objdump -D program
```

We can look at the dissassembly and see the main funtion and the echo function.
The echo funtion uses the scanf and puts functions -> which tells us this is 
the function that copies our input.

We also see a SecretFunction there ... 

The goal will be to overflow scanf in order to make a "ret" to the secret function.

NOTES: 
* secretfuntion is at address: 0x0804853b

After running and checking the program we can see thyat after 32 charecterc there is a Segmentation Fault
which means that the 33-nd char is written on the return address.

Now we need to write the address for the secret function there

```bash
python -c "print '\x90'*32 + '\x08\x04\x85\x3b'[::-1]" | ./program
```

This will run over the return address for the echo function and will make the jump to the secretfunction.
The result of this is

```
You've found the secret
The flag is: bicollateral
```
