---
description: >-
  Database configuration is done in the "insert_script.js" file in the database
  directory.
---

# Database Configuration

## Directory

**Directory to file from root directory:**

database/insert\_script.js

## Database Initialisation

Database Initialisation is done in this directory. Database is injected from the config.js file into the insert\_script.js file for the creation of new database and purging of existing databases.

```javascript
//code snippets

if (err) throw err;
//1. drop database if exist - purge records
con.query(`DROP DATABASE IF EXISTS ${database.database}`, function (err, result) {
if (err) throw err;
});
//2. create database if not exist - init database
con.query(`CREATE DATABASE IF NOT EXISTS ${database.database}`, function (err, result) {
if (err) throw err;
});
//3. select database
con.query(`USE ${database.database}`, function (err, result) {
if (err) throw err;
});
```

## Table Creation

Table creation is also done in this page. Here is the schema of the table listed below together with the javascript code executed to create the table.

**SCHEMA to create the table**

```sql
const table_name = 'product';
const create_table_script = `
CREATE TABLE ${table_name} (
id           INT           NOT NULL AUTO_INCREMENT,
name         CHAR(60)      NOT NULL DEFAULT '',
description  VARCHAR(200)  NOT NULL DEFAULT '',
price        DECIMAL(8,2)  NOT NULL DEFAULT 0.00,
PRIMARY KEY  (id));
`;
```

Javascript code for the creation of the script.

```javascript
//4. create table
con.query(create_table_script, function (err, result) {
if (err) throw err;
});
```

## Insertion of Records

Insertion of records are from the "clothing\_dataset.csv". headers will the key in the key-value pair of json to insert the records into the database. Filename is obtained from the [config.js](project-config.md) file and injected into the insert\_script.js file for the insertion process.  


For the purposes of this demo project, 500 records have been prepared.

```javascript
//5. insert records
fs.createReadStream(config.dataset_filename)
.pipe(csv())
.on('data', (row) => {
    const sql_query = "INSERT INTO product (id,name,description,price) " +
    `VALUES ("${row.id}","${row.name}","${row.description}","${row.price}")`;
    con.query(sql_query, function (err, result) {
    if (err) throw err;
    });
})
.on('end', () => {
    console.log('CSV file successfully processed');
});
```

## Changing of Records

Records may be changed directly in the clothing\_dataset.csv file. the Headers will represent the key in the key-value pair in json to be used to retrieve value to be inserted into the database.

**clothing\_dataset.csv file sample**

```javascript
id,name,description,price
1,Better Sweater 1/4-Zip - W,jackets,99.1
2,Better Sweater Jacket - W,jackets,139.2
3,Re-Tool Snap-T Pullover - W,jackets,119
4,Torrentshell 3L Jacket - W,jackets,149
5,Nano Puff Jacket - W,jackets,199
```



