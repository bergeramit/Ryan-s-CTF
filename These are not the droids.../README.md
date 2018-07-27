# Find the flag (.txt)


This challenge regards the hello.apk file. To start we need to analyze this file using apktool, which we have in out disposal.

```bash
apktool d hello.apk
```

Now we hgave a folder to work with. A quick grep for a flag yield too many results from smali sub folder, fo I went over the other directories without this folder.
I did not find anything. Next I went to the smali folder to see two subfolders, android and yanl. Android was the folder that had too much flag occurences in it so I decided to check yanl first using grep.

```bash
grep -Ri flag ./yanl
```

And in the results were: 

```
./yanl/helloworld/BuildConfig.smali:.field public static final FLAG:Ljava/lang/String; = "FLAG: harmonograph"
```
