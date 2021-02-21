# Knex

```js
import knex from 'knex';

const db = knex({
    client: 'mysql',
    connection: {
        host: process.env.DB_HOST,
        user: process.env.DB_USER,
        password: process.env.DB_PASSWORD,
        database: process.env.DB_DB
    }
});
```



```js
db('table').insert({ name: 'Foo' });
```

