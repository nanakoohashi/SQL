# MySQL Code Sheet

## Create
### CREATE TABLE
**CREATE TABLE** table_name (  
column_name **INT NOT NULL AUTO_INCREMENT PRIMARY KEY**,  
column2_name **VARCHAR(255)**,  
column3_name **DECIMAL(4,2)**,  
column4_name **CHAR(4)**)  
;  
- **NB**: CHAR = fixed length 

### CREATE INDEX
#### Create index while creating table
**CREATE TABLE** table_name (  
column_name INT,  
column_name2 VARCHAR(255),  
column_name3 VARCHAR(255),  
**INDEX**(column)  
;  
- **NB**: column is the column you want to index.
#### Create index
**CREATE INDEX** index_name ON table_name(column);

## Query and Modify
### ORDER BY
**SELECT** column_name  
**FROM** table_name  
**ORDER BY** column_name **DESC/ASC**;

### WHERE
**SELECT** column_name  
**FROM** table_name  
**WHERE** Population < 10000 **OR** Population **IS NULL**;

### LIKE
**SELECT** column_name, column_name2  
**FROM** table_name  
**WHERE** column_name **LIKE** '%island%'  
**ORDER BY** column_name;  
**Note**:
%word = ends with 'word'  
word% = starts with 'word'  
%word% = contains 'word' in any position  
a%o = contains any value that start with 'a' and ends with 'o'

### IN
**SELECT** column_name, column_name2  
**FROM** table_name  
**WHERE** column_name **IN**('a', 'b');

### INSERT INTO
#### All columns
**INSERT INTO** table_name **VALUES**(1,'a', 'wow!');  
#### Specific columns
**INSERT INTO** table_name(column_name2, column_name3) **VALUES** ('a', 'wow!');
#### Columns from other tables
**INSERT INTO** table_name(column_name, column_name2, column_name3) **SELECT** column2_name, column2_name2, column2_name3 **FROM** table_name2;

### UPDATE rows
**UPDATE** table_name  
**SET** c = 'new_row_entry'  
**WHERE** a = 2;

### DELETE rows
**DELETE FROM** table_name  
**WHERE** a = 2;

### DROP TABLE
**DROP TABLE** table_name;

### IS NULL
**SELECT** * **FROM** table_name  
**WHERE** c **IS NULL**;

