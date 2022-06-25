<h1>npm project</h1>

Initial the project</br>
```
npm init
```

Install express, middleware, database, ejs</br>
```
npm i knex pg express morgan ejs
```

Install nodemon</br>
```
npm i --save-dev nodemon
```
Change `package.json`
```
"scripts": {
    "start": "nodemon",
    "test": "echo \"Error: no test specified\" && exit 1"
  }
 ```

Create db</br>
```
createdb --echo <databaseName>
```

Init knex
```
knex init
```

Modify `./knexfile.js`</br>
```
development: {
    client: 'pg',
    connection: {
      database: 'knexpress-labs',
      username: 'nimbus-user',
      password: '123'
    },
    migrations: {
      tableName: 'migrations',
      directory: './db/migrations'
    },
    seeds: {
      directory: './db/seeds'
    }
  }
  ```
  
 Setup Migration
 ```
 knex migrate:make <MigrationName>
 ```
 
 Run Migration
 ```
knex:migrate:latest
 ```
 
 Setup Environment for database
 ```
// set environment
const environment = process.env.NODE_ENV || "development";
// load exported configurations from our knexfile.js
const config = require('../knexfile');
// grab the environment that you want to connect to
const environmentConfig = config[environment];
// require knex
const knex = require('knex');
const connection = knex(environmentConfig)

module.exports = connection
```

[Option]Setup the seeds

Create the start js
```
const express = require('express') //Express
const app = express();


//Server
const PORT = 3000;
app.listen(PORT, ()=>{
    console.log(`Server is running on http://localhost:${PORT}`....)
})

```

