# in VS exists

  - in returns a list of matching values
  - exists returns a boolean value of true and false

<br>
---
<br>

# instance/entry vs schema

  - I : Instances are the collection of information stored at a particular moment.
  - S : Schema is the overall description of the database.
  - I : The instances can be changed by certain CRUD operations as like addition, deletion of data.
  - S : The basic structure of how the data will be stored in the database is called schema.
  - I : Changes Frequently.
  - S : Does not change Frequently.	
  - I : It is the set of Information stored at a particular time.
  - S : Defines the basic structure of the database i.e how the data will be stored in the database.

<br>
---
<br>

# strong entity vs weak entity

  - A strong entity is not dependent of any other entity in the schema. 
  - A strong entity will always have a primary key. 
  - Strong entities are represented by a single rectangle. 
  - The relationship of two strong entities is represented by a single diamond.
  - Various strong entities, when combined together, create a strong entity set.
  - A weak entity is dependent on a strong entity to ensure the its existence.
  - Unlike a strong entity, a weak entity does not have any primary key. 
  - It instead has a partial discriminator key. 
  - A weak entity is represented by a double rectangle.
  - The relation between one strong and one weak entity is represented by a double diamond.
  - Strong entity have either total participation or not.	
  - While weak entity always has total participation.
 
<br>
---
<br>

#  Dirty Read Problem & Cascading Rollback / Cascading Abort / Cascading Schedule

  - When a Transaction reads data from uncommitted write in another transaction, then it is known as Dirty Read. 
  - If that writing transaction failed, and that written data may updated again. 
  - Therefore, this causes Dirty Read Problem.
  - Reading the data written by an uncommitted transaction is called as dirty read.
    - ## Cascading Rollback as a result of Dirty Read
      - If in a schedule, failure of one transaction causes several other dependent transactions to rollback or abort, then such a schedule is called as a Cascading Rollback or Cascading Abort or Cascading Schedule. 
      - It simply leads to the wastage of CPU time.
      - These Cascading Rollbacks occur because of Dirty Read problems.
      - For example, transaction T1 writes uncommitted x that is read by Transaction T2. 
      - Transaction T2 writes uncommitted x that is read by Transaction T3.
      - Suppose at this point T1 fails.
      - T1 must be rolled back, since T2 is dependent on T1, T2 must be rolled back, and since T3 is dependent on T2, T3 must be rolled back.
 
<br>
---
<br>

# Cascadeless Schedule
  - This schedule avoids all possible Dirty Read Problem.
  - In Cascadeless Schedule, if a transaction is going to perform read operation on a value, it has to wait until the transaction who is performing write on that value commits. 
  - That means there must not be Dirty Read. 
  - Because Dirty Read Problem can cause Cascading Rollback, which is inefficient.
  - Cascadeless Schedule avoids cascading aborts/rollbacks (ACA). Schedules in which transactions read values only after all transactions whose changes they are going to read commit are called cascadeless schedules. 
  - Avoids that a single transaction abort leads to a series of transaction rollbacks. 
  - A strategy to prevent cascading aborts is to disallow a transaction from reading uncommitted changes from another transaction in the same schedule.
  - All cascadeless Schedules are recoverable but not all recoverable transactions are cascadeless.
  