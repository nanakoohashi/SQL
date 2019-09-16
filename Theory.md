# SQL Theory Sheet
## Basics
- Table = Entities = Relations
- Rows = Tuples = Records
- Columns = Attributes = Fields
- **(Attribute) Domain**: Specific range of values of each column.
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
## Normal Forms
### 1NF
- Most basic of Normal Forms.
- Must contain only one piece of information.
- No duplicate rows.

### 2NF
- Dependent on PK of t1.

### 3NF
- Dependent on FK of t1.
