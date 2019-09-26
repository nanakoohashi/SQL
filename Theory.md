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
  - **Requirement**: FK may have NULL entry as long as it's NOT a part of its table's PK.
    - Every non-null FK value must reference an existing PK value.  
  - **Flags**: used to avoid NULLs and indicate the absence of some value.  
- **Entity Integrity Rules**  
  - **Requirement**: PK entries must be unique.
    - PK entries cannot be NULL.
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

## Relational Algebra
- **SELECT**: Yields values for all rows that satisfy a given condition.
- **PROJECT**: Yields values for all selected columns.
- **UNION**: Combines all rows from two tables excluding duplicate rows. Tables must be union-compatible.
- **INTERSECT**: Yields only the rows that appear on both tables (duplicates).
- **DIFFERENCE**: Yields all rows in one table that are not found in the other table.
- **PRODUCT**: Yields all possible pairs of rows from two tables (Cartesian Product).  
  - e.g. Table 1 (6 rows) x Table 2 (3 rows) = 18 rows. 
- **JOIN**
  1. **Natural Join**: links tables only selecting rows with common values in their common columns.
  2. **Equijoin**: links tables based on an equality condition compares specified columns of each table.
  3. **Inner Join**: only returns matched records from the tables that are being joined.
  4. **Outer Join**: the matched pairs would be retained and any unmatched values in the other table would be left NULL.  
    - **Left Outer Join**: yields all of the rows in table 1 including those that do not have a matching value in table 2.
    - **Right Outer Join**: yields all of the rows in table 2 including those that do not have matching values in table 1.
    
## Relationships
- 1:M is the relatinal model ideal.
- 1:1 should be rare in relational database design.
- M:N is not supported directly in the relational environment.
  - Composite entities (=bridge entity = associative entity) are a solution to M:N relationships.
### Degree of Relationship
- **Unary Relationship**: both participants in the relationship are the same entity (=table).
- **Binary Relationship**: Two entities participate -> most common.
- **Ternary Relationship**: Three entities participate.
- **Cardinality**: maximum number of times an instance of an entity can be associated with a related entity.
- **Modality**: minimum number of times a table can be associated with a related entity.

## ER Modelling
- **Required Attribute**: Column must have value; cannot be left empty.
- **Optional Attribute**: Column does not require a value; can be left empty.
- **Identifiers**: Primary Key.
- **Composite Identifiers**: A primary key composed of more than one attribute.
- **Single-valued Attribute**: Attribute that can only have a single value. *e.g. SSN*
- **Multi-valued Attribute**: Attribute that can have many values. *e.g. a person may have several college degrees.

### Types of Attributes
- **Simple Attribute**: Cannot be subdivided.
- **Composite Attribute**: Can be subdivided to yield additional attributes.
- **Derived Attribute**: Attribute whose value is calculated (derived) from other attributes.
  - **Advantages**
    - Saves CPU
    - Saves data access time
    - Data value easily accessible
    - Can keep track of historical data
    - Saves storage space
    - Computation always yields current value
  - **Disadvantages**
    - Requires constant maintenance
    - Uses CPU processing cycles
    - Adds coding complexities to queries
- **Existence Dependence**: An entity that can only exist in the database when it is associated with another related entity occurrence.
- **Existence Independence**: = strong entity = regular entity.
- **Weak (non-identitying) Relationships**: Primary key of the related entity does not contain a primary key component of the parent entity.
- **Strong (identifying) Relationship**: PK of related entity contains PK component of parent entity.
- **Weak Entities**:
 1. Entity is existence-dependent.
 2. Entity has PK that is partially/totally derived from the parent entity.
- **Optional participation**: one entity occurrence does not require a corresponding entity occurrence.

## Basic SQL
- **DDL (Data Definition Language)**: commands that create database objects (tables, indexes). 
## Normal Forms
### 1NF
- Most basic of Normal Forms.
- Must contain only one piece of information.
- No duplicate rows.

### 2NF
- Dependent on PK of t1.

### 3NF
- Dependent on FK of t1.
