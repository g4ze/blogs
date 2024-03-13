---
title: "PostgreSQL and Node.js: Building a Strict and Consistent Database Schema with TypeScrip"
datePublished: Wed Mar 13 2024 14:09:35 GMT+0000 (Coordinated Universal Time)
cuid: cltpvnzrj000009jy9bzqap48
slug: postgresql-and-nodejs-building-a-strict-and-consistent-database-schema-with-typescrip
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1710338924582/9476bb22-4a4c-4d46-a8e1-947847e3e6bb.jpeg
tags: postgresql, nodejs, databases, sql

---

Take reference from this [code base](https://github.com/g4ze/sql).

A strict and consistent data base is the best part about a sql database. The point being, devs are dumb and we should have something smart enough to let the dumb bitches know that the data they be sending is trashy and inconsistent. One can implement such schema based strictness on the backend server level using something like mongoose or zod, but the point is, the database itself is not the one rejecting faulty schemas, like mongoDB or any non relational db.

So let's check out how good sql dbs help us with such a problem

spin up the docker postgress via: `docker run --name my-postgres -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres`

the connection string should be like: `postgresql://postgres:`[`mysecretpassword@localhost:5432`](mailto:mysecretpassword@localhost:5432)`/postgres?sslmode=disable`

You can install and run `psql` if you wan to directly communicaate with the db thru a shell, but we will be using the node.js library `pg` for our casual endevour.

A normal query would look like this:

```plaintext
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP
);
```

All the keyword are pretty self explanatory here.

1. CREATE TABLE users CREATE TABLE users: This command initiates the creation of a new table in the database named users.
    
2. id SERIAL PRIMARY KEY id: The name of the first column in the users table, typically used as a unique identifier for each row (user). Similar to \_id in mongodb SERIAL: A PostgreSQL-specific data type for creating an auto-incrementing integer. Every time a new row is inserted, this value automatically increments, ensuring each user has a unique id. PRIMARY KEY: This constraint specifies that the id column is the primary key for the table, meaning it uniquely identifies each row. Values in this column must be unique and not null.
    
3. email VARCHAR(255) UNIQUE NOT NULL, email: The name of the second column, intended to store the user's username. VARCHAR(50): A variable character string data type that can store up to 50 characters. It's used here to limit the length of the username. UNIQUE: This constraint ensures that all values in the username column are unique across the table. No two users can have the same username. NOT NULL: This constraint prevents null values from being inserted into the username column. Every row must have a username value.
    
4. password VARCHAR(255) NOT NUL Same as above, can be non uniqye
    
5. created\_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT\_TIMESTAMP created\_at: The name of the fifth column, intended to store the timestamp when the user was created. TIMESTAMP WITH TIME ZONE: This data type stores both a timestamp and a time zone, allowing for the precise tracking of when an event occurred, regardless of the user's or server's time zone. DEFAULT CURRENT\_TIMESTAMP: This default value automatically sets the created\_at column to the date and time at which the row is inserted into the table, using the current timestamp of the database server.
    

### This is how some CRUD commands would look like in play:

1. INSERT INSERT INTO users (username, email, password) VALUES ('username\_here', '[user@example.com](mailto:user@example.com)', 'user\_password'); 💡 Notice how you didn’t have to specify the id because it auto increments
    
2. UPDATE
    

```plaintext
UPDATE users
SET password = 'new_password'
WHERE email = 'user@example.com';
```

3. DELETE
    

```plaintext
DELETE FROM users
WHERE id = 1;
```

4. Select
    

```plaintext
SELECT * FROM users
WHERE id = 1;
```

We're all set to fly into out node app and fet things running `pg` library [https://www.npmjs.com/package/pg](https://www.npmjs.com/package/pg) is a Non-blocking PostgreSQL client for Node.js.

### Connecting -

```plaintext
import { Client } from 'pg'
 
const client = new Client({
  host: 'my.database-server.com',
  port: 5334,
  database: 'database-name',
  user: 'database-user',
  password: 'secretpassword!!',
})

client.connect()
```

### Querying -

```plaintext
const result = await client.query('SELECT * FROM USERS;')
console.log(result)
 
// write a function to create a users table in your database.
import { Client } from 'pg'
 
const client = new Client({
  connectionString: "postgresql://postgres:mysecretpassword@localhost/postgres"
})

async function createUsersTable() {
    await client.connect()
    const result = await client.query(`
        CREATE TABLE users (
            id SERIAL PRIMARY KEY,
            username VARCHAR(50) UNIQUE NOT NULL,
            email VARCHAR(255) UNIQUE NOT NULL,
            password VARCHAR(255) NOT NULL,
            created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP
        );
    `)
    console.log(result)
}

createUsersTable();
```

We're not gonna be a cry baby here and use typsecript for implmentaion code.

```plaintext
npm init -y
npx tsc --init
```

### Change the rootDir and outDir in tsconfig.json

"rootDir": "./src", "outDir": "./dist", Install the pg library and it’s types (because we’re using TS)

```plaintext
npm install pg
npm install @types/pg```
```