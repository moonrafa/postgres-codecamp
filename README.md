login
```
  psql --username=freecodecamp --dbname=postgres
```
list databases
```
  \l
```
create database
```
CREATE DATABASE database_name;
```
rename database
```
ALTER DATABASE database_name RENAME TO new_database_name;
```
delete database
```
DROP database_name;
```
connect to database
```
\c database_name
```
display tables/specific table
```
\d
\d table_name
```
create table
```
CREATE TABLE table_name();
```
add column
```
ALTER TABLE table_name ADD COLUMN column_name DATATYPE;
ALTER TABLE table_name ADD COLUMN column_name DATATYPE NOT NULL;
ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL;


```
remove column
```
ALTER TABLE table_name DROP COLUMN column_name;
```
rename a column
```
ALTER TABLE table_name RENAME COLUMN column_name TO new_name;
```
insert data
```
INSERT INTO table_name(column_1, column_2) VALUES(value1, value2);
INSERT INTO table_name(column_1, column_2) VALUES(value1, value2), (value1, value2);

```
if varchar = use 'between quotes'

view data from table 
```
SELECT columns FROM table_name;
```
asterisk(*) = all
  
delete row from table
```
DELETE FROM table_name WHERE condition;
```
ex: WHERE username='Luigi'

delete table
```
DROP TABLE table_name;
```
SERIAL TYPE = INT, NOT NULL, AUTO_INCREMENT
NUMERIC(4, 1) = decimals. up to four digits and one of them has to be to the right of the decimal ex: 1,2.

change value
```
UPDATE table_name SET column_name=new_value WHERE condition;
```
order table
```
SELECT columns FROM table_name ORDER BY column_name;
```
uniquely identify a row in the table
```
ALTER TABLE table_name ADD PRIMARY KEY(column_name);
```
drop constraint
```
ALTER TABLE table_name DROP CONSTRAINT constraint_name;
```
set a foreign key so you can relate rows from this table to rows from your other tables
```
ALTER TABLE table_name ADD COLUMN column_name DATATYPE REFERENCES referenced_table_name(referenced_column_name);
```
To set a row in more_info for Mario, you just need to set the character_id (foreign key) value to whatever it is in the characters table
These tables have a "one-to-one" relationship. One row in the characters table will be related to exactly one row in more_info and vice versa. Enforce that by adding the UNIQUE constraint to your foreign key.
```
ALTER TABLE table_name ADD UNIQUE(column_name);
```