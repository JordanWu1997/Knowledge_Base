Tags: #Database
Vimwiki: :Database:

______________________________________________________________________

# Database

- References
  - https://en.wikipedia.org/wiki/First_normal_form
  - https://www.youtube.com/watch?v=-WEpWH1NHGU
  - https://www.youtube.com/watch?v=GFQaEYEc8_8&list=WL&index=93
  - https://www.javatpoint.com/dbms-normalization

## Normalization For Relational Database

Procedure to prevent duplicate recording storage in database.
Make database easier to be maintained but not necessarily human-reading friendly.

### 1st Normal Form (1NF)

Prevent column with multiple values.
Single value stored in one single column (also no mixed datatype allowed).
Use primary key to present each rows

### 2nd Normal Form (2NF)

Prevent duplicate recording in tables.
Remove related columns into other tables.
Split big table into multiple small table and relates those with columns (key)
Prevent multiple columns that store relational data (duplicate recording)
Each non-key attribute must depend on the entire primary key

### 3rd Normal Form (3NF)

Make sure that columns that are not keys do not have relation with each other
Every non-key attribute in a table should depend on the key, the whole key, and nothing but the key

### Boyce-Codd Normal Form (BCNF)

Every attribute in a table should depend on the key, the whole key, and nothing but the key

### 4th Normal Form (4NF)

No multi-valued key dependency

### 5th Normal Form (5NF)

The table in 4NF cannot be describable as the logical result of joining some other tables together
No join dependency

## De-normalization For Relational Database

## Data Integrity

## Transaction

### ACID property

- `Atomicity`
- `Consistency`
- `Isolation`
- `Durability`

### Transaction Isolations

### Rollback

## Lock

### Dead Lock

### Race Condition

## Security

### SQL Injection

- https://www.youtube.com/watch?v=Y4hhCscSpe8
- https://github.com/OneEqualsOne/SecurityNotes/blob/main/SQL%20Injection.md
- https://pentestmonkey.net/category/cheat-sheet/sql-injection
- `Authentication Bypass`
- `UNION Intejection`
- `Blind Injection`
