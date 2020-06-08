# cron

`minute / hour / dOM / month / dOW`



global:

-   `*` — any value
-   `,` — set of values
-   `-` — value range



-   minute
    -   `1`–`59`
-   hour
    -   `0`–`23`
-   dOM
    -   `1`–`31`
-   month
    -   `1`–`12`
    -   `JAN`–`DEC`
-   dOW
    -   `0`–`6`
    -   `SUN`–`SAT`



```
# For scripts that don't need root privileges
crontab -e
```

```
# For scripts that need to be run as root
sudo crontab -e 
```



```
0 0 * * * command
0 0 1 * * certbot renew
```



## Links

-   https://crontab.guru