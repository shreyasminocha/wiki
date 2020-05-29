# SQL Queries

Some illustrative examples follow. Usually it will be obvious what the query is doing.

```sql
select a, b, c from table;
```

```sql
select * from table;
```

```sql
select distinct city from table;
```

```sql
select distinct city, country from table;
```

```sql
select first_name, last_name from students where marks > 80;
```

```sql
select first_name, last_name from students where marks != 42;
```

```sql
select first_name, last_name from students where marks between 80 and 90;
```

```sql
select city from table where amount > 5000 and tax < 50;
```

```sql
select score from table where name == "Shreyas" or name == "Sister";
```

```sql
select score from table where name in ("Shreyas", "Sister");
```

```sql
select score from table where name in (select first_name from family);
```

```sql
select customer_name, commodity, price from commodities order by price desc, customer, commodity asc;
```

```sql
select name from customers where phone_number is not null;
```

```sql
update customers set bonus_points = 0, redeemed_points = 0 where id = 25;
```

> If you omit the `where` clause in an `update` statement, ALL records will be updated!

```sql
delete from customers where first_name="Jeff";
```

> If you omit the `where` clause in a `delete` statement, ALL records will be deleted!

```sql
delete from customers;
```

```sql
select first_name, city from customers limit 50;`
```

The `limit` syntax is MySQL-specific.

```sql
select employee_id, max(shipping_fee) from orders;
```

```sql
select min(price) from inventory;
```

```sql
select max(price) from inventory;
```

```sql
select avg(price) from inventory;
```

```sql
select sum(price) from inventory;
```
