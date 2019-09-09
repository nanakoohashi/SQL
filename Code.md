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

### Primary Key and Auto-Increment
**CREATE TABLE** table_name (
table_name INT **AUTO_INCREMENT PRIMARY KEY*);

### ALTER TABLE
#### Add
**ALTER TABLE** table_name  
**ADD** column_name VARCHAR(10);  
#### Drop  
**ALTER TABLE** table_name  
**DROP** column_name;  
#### Choose where to add column
**ALTER TABLE** table_name
**ADD** column_name VARCHAR(10) **AFTER** other_column_name;

### Format date
**SELECT DATE_FORMAT**(Now(), '%W, %D, %M, %Y');

## Aggregate Functions
### DISTINCT
**SELECT** COUNT(**DISTINCT** Continent) **FROM** Country;
## Triggers
### Create Trigger
**CREATE TRIGGER** trigger_name **AFTER INSERT ON**  table_name  
**FOR EACH ROW**  
**UPDATE** table_name2 **SET** last_order_id = New.id  
**WHERE** id = New.Customer.id  
  
  Other options:
  - BEFORE INSERT
  - BEFORE UPDATE
  - BEFORE DELETE
  - AFTER INSERT
  - AFTER UPDATE
  - AFTER DELETE
  
 ## Stored Function
 **CREATE FUNCTION** track_len (seconds INT)  
 **RETURNS** VARCHAR(16)  
 **RETURN CONCAT_WS;
 
 ## Stored Procedure
**DELIMITER //**  
**CREATE PROCEDURE** procedure_name()  
**BEGIN**  
**SELECT** * FROM table_name;  
**END //**  
**DELIMITER ;**
