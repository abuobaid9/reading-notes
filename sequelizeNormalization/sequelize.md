# Sequelize Normalization

Sequelize is a promise-based, Node.js ORM (Object-relational mapping) for Postgres, MySQL, MariaDB, SQLite and Microsoft SQL Server. It features solid transaction support, relations, eager and lazy loading, read replication, and more.

## What is an ORM
An ORM is known as Object Relational Mapper. This is a tool or a level of abstraction which maps(converts) data in a relational database into programmatic objects that can be manipulated by a programmer using a programming language(usually an OOP language). ORMs solely exist to map the details between two data sources which due to a mismatch cannot coexist together.

## Benefits of using ORMs
ORMs save time in writing raw SQL queries thereby reducing development time.

SQL queries are written as strings and embedded in the application logic. It is very difficult to get tools like syntax highlighting, autocorrect, or Intellisence support while writing raw queries in an application. ORMs provide a type-safe interface for interacting with databases.

ORMs helps to prevent against SQL injections.

ORMs lets you write Object-oriented code for your models and abstracts away the complete CRUD process enabling you to write declarative code in your application.

## Features of Sequelize

Sequelize is packed with lots of features, below are a couple of features we will cover in this series on sequelize and more.

* Promises.
* Support for MySQL, SQLite, PostgreSQL, and Microsoft SQL server.
* Model Hooks
* Transaction support
* Database synchronization
* Database migrations
* Model Validations
* Raw queries
* Data seeding
* Scopes
