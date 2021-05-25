# Normalization 

- used to remove or atleast reduce redundancy in database
- there are 2 types of Duplicacies in DBMS
  - Row Level Duplicacy 
    - can be removed by using primary keys
  - Column Level Duplicacy
    - can be removed or atleast reduced by using Normalizaing the Database

- ## Why is Column Level Duplicacy bad?
  - It brings the folloing anomalies
    - ### Insertion Anomaly
    - ### Deletion Anomaly
    - ### Updation Anomaly

<br>
---
<br>

## First Normal Form (1NF)

  - Table must not have any multivalue attributes
  - To convert a table into First Normal Form, there are 3 ways
    - split the multivalue attribute rowise and make a composite primary key of say the original PK with the multivalued attribute
    - make multiple columns if the number of choices in multivalued attributes are fixed (very bad choice, because if many multivalued attributes, a many nulls)
    - make 2 seperate tables - base table and referencing table (better way of implementation)


## Second Normal Form (2NF)

  - table must be in 1NF
  - the table must not contain any partial dependency
  - all non-prime attributes should be fully functional dependent on candidate key
  - a simple example can be a table with the following attributes: 
    - Entity Name: Customer
    - Attributes: CustID, StoreID, Location
  - here location is non-prime attribute
  - CustID + StoreID = PK (Composite)
  - Store must be fully functional dependent on the PK, but it is not. 
  - it is actually dependend only StoreID
  - ## How to convert in 2NF?
    - split tables
    - 1 table CustID & StoreID
    - 1 table StoreID & Location

## Third Normal Form (3NF)

  - table must be in 2NF
  - must NOT have any transitive dependency
  - example
    - Entity Name: student
    - Attributes: RollNo, State, City
    - RollNo -> State, State -> City, RollNo -> City
    - Transitive, because state is non-prime, and through that, we are determining City
    - Hence, not a 3rd normal form.
  - For each FD, 
    - LHS => is CK or SK
    - OR
    - RHS => is Prime Attribute


## Boyce Codd Normal Form (BCNF)

  - table must be in 3NF
  - LHS of each FD must be a CK or SK
  