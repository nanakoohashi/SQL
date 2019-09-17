# SQL Theory Sheet
## Basics
- Table = Entities = Relations
- Rows = Tuples = Records
- Columns = Attributes = Fields
- **(Attribute) Domain**: Specific range of values of each column.
- **Determination**: Knowing the value of one column makes it possible to determine the value of another.  
  - **Functional Dependence**: The value of one or more columns determines the value of one or more other columns.  
    - **Determinant**: The column whose value determines another.  
                      *STU_NUM -> STU_NAME*
    - **Dependent**: The column whose value is determined by the other.  
- **Referential Integrity**: The condition in which **every reference to a row by another table is valid**, i.e. every foreign key must either be null or a vaid value in the primary key of the related table.
## Keys
### Primary Key
A column that *uniquely indentifies* any given row.
### Composite Key
Comprised of *more than one column*. Part of key attribute.  
- e.g. (STU_LNAME, STU_FNAME, STU_PHONE) -> STU_HRS
### Superkey
A theoretical key that can *uniquely identify any row* in a table. It can be a combination of columns. 
### Candidate Key
A column or set of columns in a table that uniquely identifies any database row without referring to other data.
  - A minimal superkey without any unnecessary attributes (theoretical).
### Foreign Key
The primary key of one table that has been placed into another table to create a **common attribute**. Used to ensure referential integrity.
### Secondary Key
Used strictly for **data retrieval purposes** (it is kind of an index, theoretical).

## Rules

## Normal Forms
### 1NF
- Most basic of Normal Forms.
- Must contain only one piece of information.
- No duplicate rows.

### 2NF
- Dependent on PK of t1.

### 3NF
- Dependent on FK of t1.
