In this scenario, we are going to teach our users how to make use of the autocommit, Commit, and Rollback functions introduced in InnoDB

Typically individual DML (Insert, Update, Delete) statements are performed in an autocommit transaction, 
which those commands are committed as soon as the statement successfully completes. 
There will be no opportunity to roll back the database to the state prior to the statement if autocommit is enabled. 
When something goes wrong, the only restoration option available is to reconstruct the data from a backup (providing one exists).

In MySQL, autocommit is on by default for InnoDB, here in this case, we are going to teach you how to disable this option.

Secondly, after seting up a MYSQL enviroment, we will create a testing database and table for experiment:

 Create a table inside the database

 `CREATE DATABASE testDB;`{{execute}} 
 
 `START TRANSACTION;`{{execute}} 

 `use testDB;`{{execute}} 

 `CREATE TABLE tester (age INT, name CHAR (20), INDEX (age));`{{execute}} 

 `show tables;`{{execute}} 

 Insert show orgin info inside
 `INSERT INTO tester VALUES (10, 'Alice');`{{execute}} 

 `SELECT * FROM tester;`{{execute}}
 
 After finsihed the information setup, we will process the ROLLBACK funactions:
 First, we will using <pre>COMMIT</pre>
 Create a save log here.
 `COMMIT;`{{execute}} 

 `SET autocommit=0;`{{execute}} 

 Assume some people change the info inside
 `INSERT INTO tester VALUES (10, 'Bob');`{{execute}} 

 `INSERT DELETE tester VALUES (10, 'Alice');`{{execute}} 

 `SELECT * FROM tester;`{{execute}}

 `ROLLBACK;`{{execute}}

 After that check it again.
 `SELECT * FROM tester;`{{execute}}




<pre>
[ -d /home/scrapbook/tutorial/.git ] && echo "done"
</pre>

If you run `git init`{{execute}}, you will be allowed to continue.

The `index.json` example is:
<pre>
"details": {
    "steps": [
        {
            "title": "Step 1 - Verify",
            "text": "step1.md",
            "verify": "step1-verify.sh"
        }
    ]
}
</pre>
