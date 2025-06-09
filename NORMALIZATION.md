# NORMALIZATION

* It is a methodology used to provide a frame work for structuring relational databases by reducing data redundancy, data dependencies and improve data integrity.

## DATA REDUNDANCY
* This is duplication of the same data in multiple tables.

  ### PROS OF INTENTIONAL REDUNDANCIES
-  Beneficial for disaster recovery and ensuring data consistency.

   ### CONS OF REDUNDANCIES
- Depletes memory space and leads to slower querying and high costs
- Leads to data corruption
- Inconsistencies

## DATA INTEGRITY
* This is data reliability accuracy and completeness over its life cycle period . It means that data accessed now will be the same data accessed after a long period of time if no update is made to the data.
* This includes maintaining of data quality and consistency.
* Data integrity can be categorized into
  - Entity integrity - Ensures primary keys are unique and not null
  - Referential Integrity - Maintains relationships between tables by ensuring foreign keys match primary keys
  - Domain Integrity - Enforces values allowed in columns
  - User-defined Integrity - allows for additional constraints based on specific business rules.

## ANOMALIES 
* These are inconsistencies or errors that occur during data operations such as insertion, deletion or updates leading to  data integrity issues

 ### TYPES OF ANORMALIES
1. Update anomalies
2. Insertion anomalies
3. Deletion anomalies

#### Update Anomalies
-  This maybe as a result of data being updated partially and other fail  to be updated in multiple places hence when a query is made, different answers respond to the same query.

#### Insertion Anomalies
- This is finding trouble in adding new records to a table because of how data has been structured.

#### Deletion Anomalies
- This is when if you delete data holding one fact leads to deletion of data holding another fact.
    
> N/B -  You should be able to add new types of data to a database without changing its structure too much. Otherwise, each change in structure could potentially break existing applications that interact with the database.

## THE NORMALIZATION FORMS
### First Normalization Form
* Every record/row must be unique
* Each cell contains only one value

### Second Normalization Form
* Ensure that the table is in 1NF
*  All attributes ( columns that are keys) are dependent on the primary keys. This means that if you have columns that are related to each other or to data but not the primary key, then they belong to a different table.

### Third Normalization Form
* Ensure that the table is in 2NF
*All columns can be determined only by the key in the table and not by any other column.
* If such an entity exists, move it outside into a new table.

### Boyce-Codd Normal Form
*  Is a type of normalization which removes all redundancies based on functional dependencies
*  It is a slightly stricter version of the third normal form (3NF)

### Forth Normalization Form
* Ensure that the table is in BCNF
* It doesn't allow any multi-valued dependencies. Rather than storing multi-valued dependencies on one table, they are put each in their own tables.

### Fifth Normalization Form
* Ensure that the table is in 4NF
* It doesn't  join dependencies that are not implied by the candidate keys. This ensures that the table cannot be decomposed further without losing information..


> N/B - Higher normal forms beyond 3NF are mainly of academic interest and are rarely applied in practice due to potential performance issues.


# ACID PROPERTIES
* It stands for Atomicity, Consistency, Isolation and durability

Atomicity: Ensures that a transaction is treated as a single unit . This means that ALL operations within a transaction must be completed successfully for the transaction to be committed.
* If any part of the transaction fails, the entire transaction is rolled back, leaving the database in a consistent state.

## Consistency:
+ Ensures that a transaction will take the database from one valid state to another, without violating any integrity constraints. This means that after a transaction completes, the database remains in a consistent state.

## Isolation:
+ Ensures that transactions occur independently of each other. Simultaneous states of transactions are not visible to other transactions, preventing issues like dirty reads, non-repeatable reads, and phantom reads.

## Durability:
+ Once a transaction is committed, its effects are permanent and survive system failures and aSny changes made by a committed transaction are stored in the database and cannot be undone unless explicitly rolled back.
