# SQL Vs NoSQL :-

| SQL      |      NoSQL      |  
|----------|:-------------:|
| Data uses Schemas |  Schemas-less |
| Relations | No (or very few) Relations  |
| Data is distributed acroos multiple tables | Data is typically merged / nested in a few collections |
| Horizontal scaling is difficult/impossible;Vertical sacling is possible | Both Horizontal and Vertical scaling is possible |
|Limnitations for lots of (thousands) read & write queries per second| Great performance for mass (simple) read & write requests|

---
---

## Horizontal scaling  Vs  Vertical sacling :-

| Horizontal scaling    |   Vertical sacling |
|----------|:-------------:|
| Add More Servers( and merge Data into one Database )|  Improve Server Capacity / Hardware  |

---

## Examples :-

- SQL database examples: MySql, Oracle, Sqlite, Postgres and MS-SQL.
- NoSQL database examples: MongoDB, BigTable, Redis, RavenDb, Cassandra, Hbase, Neo4j and CouchDb.

---

SQL Examples :-
---

## What is MySQL ?

     MySQL database is very popular open-source database. It is generally been stacked with apache and PHP, although it can be also stacked with nginx and server side javascripting using Node js.

## What is MS-SQL ?

     It is a powerful and user friendly database which has good stability, reliability and scalability with support from Microsoft.

## What is  Oracle ?

     It is a limited edition of Oracle Enterprise Edition server with certain limitations. This database is free for development and deployment.

NoSQL Examples :-
---

## What is MongoDB ?

     Mongodb is one of the most popular document based NoSQL database as it stores data in JSON like documents. It is non-relational database with dynamic schema. It has been developed by the founders of DoubleClick, written in C++ and is currently being used by some big companies like The New York Times, Craigslist, MTV Networks. 

## What is CouchDB ?

     CouchDB is also a document based NoSQL database. It stores data in form of JSON documents.

## What is Redis ?

     Redis is another Open Source NoSQL database which is mainly used because of its lightening speed. It is written in ANSI C language.

---

## Sequelize v6 :-

    Sequelize is a promise-based Node.js ORM tool for Postgres, MySQL, MariaDB, SQLite, Microsoft SQL Server, Amazon Redshift and Snowflake’s Data Cloud. It features solid transaction support, relations, eager and lazy loading, read replication and more.

-Ex :

```js
const { Sequelize, Model, DataTypes } = require('sequelize');
const sequelize = new Sequelize('sqlite::memory:');

class User extends Model {}
User.init({
  username: DataTypes.STRING,
  birthday: DataTypes.DATE
}, { sequelize, modelName: 'user' });

(async () => {
  await sequelize.sync();
  const jane = await User.create({
    username: 'janedoe',
    birthday: new Date(1980, 6, 20)
  });
  console.log(jane.toJSON());
})();
```
