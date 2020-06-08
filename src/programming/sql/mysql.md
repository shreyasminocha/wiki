# MySQL

>   My S-Q-L

```sh
mysql -u root -p
```



## Shell

### Create user

```mysql
 create user 'someuser' identified by 'password';
```

### Create DB

```mysql
create database somedb;
grant all privileges on somedb.* to 'someuser';
flush privileges;
```

### Change user password

```mysql
 alter user 'someuser' identified by 'password';
```

## Export and Import

```sh
mysqldump -u someuser --password somedb > somedb.sql
```

```
mysql -u someuser --password somedb < somedb.sql
```

