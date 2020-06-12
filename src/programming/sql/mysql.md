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

## Troubleshooting

### Authentication

#### Client does not support authentication protocol

```mysql
alter user 'user'@'localhost' identified by 'new_pwd'; 
alter user 'user'@'localhost' identified with mysql_native_password BY 'new_pwd';
```

—[TIAGO SILVA](https://stackoverflow.com/a/53463633)

### Connection

