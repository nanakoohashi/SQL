# MySQL Code Sheet

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
  
*Note: 
%word = ends with 'word'  
word% = starts with 'word'  
%word% = contains 'word' in any position  
a%o = contains any value that start with 'a' and ends with 'o'*