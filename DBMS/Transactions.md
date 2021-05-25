# Transactions

- A transaction is a set of logically related operations.
- A transaction is a single logical unit of work which accesses and possibly modifies the contents of a database. 
- Transactions access data using read and write operations. 

<br>
---
<br>

# Schedule

- A chronological execution sequence of a transaction is called a schedule. A schedule can have many transactions in it, each comprising of a number of instructions/tasks.

  - ## Serial Schedule
    - It is a schedule in which transactions are aligned in such a way that one transaction is executed first. When the first transaction completes its cycle, then the next transaction is executed. Transactions are ordered one after the other.


<br>
---
<br>


# Transaction States

- A transaction in DBMS can be in one of the following states

  - ## Active
    - a transaction is in execution is said to be in active state. 
    - it doesn’t matter which step is in execution, until unless the transaction is executing, it remains in active state. 
  - ## Partially Committed
    - a transaction goes into “partially committed” state from the active state when there are read and write operations present in the transaction. 
    - a transaction contains number of read and write operations. 
    - once the whole transaction is successfully executed, the transaction goes into partially committed state where we have all the read and write operations performed on the main memory (local memory) instead of the actual database.
    - the reason why we have this state is because a transaction can fail during execution so if we are making the changes in the actual database instead of local memory, database may be left in an inconsistent state in case of any failure. 
    - this state helps us to rollback the changes made to the database in case of a failure during execution.
  - ## Committed
    - If a transaction completes the execution successfully then all the changes made in the local memory during partially committed state are permanently stored in the database. You can also see in the above diagram that a transaction goes from partially committed state to committed state when everything is successful.
  - ## Failed
    - If a transaction is executing and a failure occurs, either a hardware failure or a software failure then the transaction goes into failed state from the active state. 
  - ## Aborted
    - As we have seen above, if a transaction fails during execution then the transaction goes into a failed state. 
    - The changes made into the local memory (or buffer) are rolled back to the previous consistent state and the transaction goes into aborted state from the failed state. 

<br>
---
<br>

# ACID Properties

- In order to maintain consistency in a database, before and after the transaction, certain properties are followed. 
- These are called ACID properties. 


  - ## Atomicity
    - By this, we mean that either the entire transaction takes place at once or doesn’t happen at all.
    - There is no midway i.e. transactions do not occur partially. Each transaction is considered as one unit and either runs to completion or is not executed at all. 
    - It involves the following two operations.
      - Abort: If a transaction aborts, changes made to database are not visible
      - Commit: If a transaction commits, changes made are visible.
    - Atomicity is also known as the ‘All or nothing rule’. 

  - ## Consistency
    - This means that integrity constraints must be maintained so that the database is consistent before and after the transaction.
    - It refers to the correctness of a database.

  - ## Isolation
    - This property ensures that multiple transactions can occur concurrently without leading to the inconsistency of database state. 
    - Transactions occur independently without interference.
    - Changes occurring in a particular transaction will not be visible to any other transaction until that particular change in that transaction is written to memory or has been committed. 
    - This property ensures that the execution of transactions concurrently will result in a state that is equivalent to a state achieved these were executed serially in some order. 

  - ## Durablity
    - This property ensures that once the transaction has completed execution, the updates and modifications to the database are stored in and written to disk and they persist even if a system failure occurs. These updates now become permanent and are stored in non-volatile memory.
    - The effects of the transaction, thus, are never lost.
    - The ACID properties, in totality, provide a mechanism to ensure correctness and consistency of a database in a way such that each transaction is a group of operations that acts a single unit, produces consistent results, acts in isolation from other operations and updates that it makes are durably stored.

<br>
---
<br>

# Transaction Control Commands

  - ## COMMIT
    - used to save changes invoked by a transaction to the database
    -  saves all the transactions to the database since the last COMMIT or ROLLBACK command
  - ## ROLLBACK
    - used to undo transactions that have not already been saved to the database
    - can only be used to undo transactions since the last COMMIT or ROLLBACK command was issued
  - ## SAVEPOINT
    - is a point in a transaction when you can roll the transaction back to a certain point without rolling back the entire transaction
    - serves only in the creation of a SAVEPOINT among all the transactional statements.
    - The ROLLBACK command is used to undo a group of transactions.

<br>
---
<br>

# Concurrent Execution

  - In a multi-user system, multiple users can access and use the same database at one time, which is known as the concurrent execution of the database. 
  - It means that the same database is executed simultaneously on a multi-user system by different users.

  - ## Problems with Concurrent Execution
    - ### [1] Lost Update Problems (W - W Conflict)
      - The problem occurs when two different database transactions perform the read/write operations on the same database items in an interleaved manner (i.e., concurrent execution) that makes the values of the items incorrect hence making the database inconsistent.
    
    - ### [2] Dirty Read Problems (W-R Conflict)
      - The dirty read problem occurs when one transaction updates an item of the database, and somehow the transaction fails, and before the data gets rollback, the updated database item is accessed by another transaction. There comes the Read-Write Conflict between both transactions.
      
    - ### [3] Unrepeatable Read Problem (W-R Conflict)
      - Also known as Inconsistent Retrievals Problem that occurs when in a transaction, two different values are read for the same database item.

<br>
---
<br>

# Concurrency Control

  - The concurrency control protocols ensure the atomicity, consistency, isolation, durability and serializability of the concurrent execution of the database transactions.
  - Therefore, these protocols are categorized as:
  
    - ## Lock Based Concurrency Control Protocol
      - There are 2 types of Locks
      - ### Shared Lock
        - It is also known as a Read-only lock. In a shared lock, the data item can only read by the transaction.
        - It can be shared between the transactions because when the transaction holds a lock, then it can't update the data on the data item.
      - ### Exclusive Lock
        - In the exclusive lock, the data item can be both reads as well as written by the transaction.
        - This lock is exclusive, and in this lock, multiple transactions do not modify the same data simultaneously.
    - There are 4 types of Lock Protocls available
      - ### Simplistic lock protocol
        - It is the simplest way of locking the data while transaction. 
        - Simplistic lock-based protocols allow all the transactions to get the lock on the data before insert or delete or update on it. 
        - It will unlock the data item after completing the transaction.
      - ### Pre-claiming Lock Protocol
      - ### Two-phase locking (2PL)
      - ### Strict Two-phase locking (Strict-2PL)
    - ## Time Stamp Concurrency Control Protocol
    - ## Validation Based Concurrency Control Protocol
    

