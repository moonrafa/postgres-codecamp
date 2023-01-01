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
CREATE TABLE table_name(column_name DATATYPE CONSTRAINTS, column_name DATATYPE CONSTRAINTS);

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
add to a related table (foreign key)
//You can use NULL or simply not include the null columns when inserting.
```
INSERT INTO more_info(birthday, height, weight, character_id) VALUES('1981-07-09',155,64.5, 1);
```
+--------------+------------+--------+--------+--------------+
| more_info_id |  birthday  | height | weight | character_id |
+--------------+------------+--------+--------+--------------+
|            1 | 1981-07-09 |    155 |   64.5 |            1 |
+--------------+------------+--------+--------+--------------+

using a condition to find something

```
SELECT columns FROM table_name WHERE condition;
```
** one to many relationship
one-to-many" relationship because one character will have many sounds, but no sound will have more than one character
** many to many relationship
many-to-many" relationship with the characters table. This is because many of the characters can perform many actions. You will see why you don't need a foreign key later
Many-to-many" relationships usually use a junction table to link two tables together

add foreign-key to a column (there can be more than one foreign-keys)
```
ALTER TABLE table_name ADD FOREIGN KEY(column_name) REFERENCES referenced_table(referenced_column);
```

composite primary key
```
ALTER TABLE table_name ADD PRIMARY KEY(column1, column2);
```
get all data from both tables

```
SELECT columns FROM table_1 FULL JOIN table_2 ON table_1.primary_key_column = table_2.foreign_key_column;
```
ex: select * from characters full join more_info on characters.character_id = more_info.character_id;

join three tables
```
SELECT columns FROM junction_table
FULL JOIN table_1 ON junction_table.foreign_key_column = table_1.primary_key_column
FULL JOIN table_2 ON junction_table.foreign_key_column = table_2.primary_key_column;
```
