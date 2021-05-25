# Recovery

- When a system crashes, it may have several transactions being executed and various files opened for them to modify the data items.

- Transactions are made of various operations, which are atomic in nature.

- But according to ACID properties of DBMS, atomicity of transactions as a whole must be maintained, that is, either all the operations are executed or none.

- When a DBMS recovers from a crash, it should maintain the following −

  - It should check the states of all the transactions, which were being executed.
  - A transaction may be in the middle of some operation; the DBMS must ensure the atomicity of the transaction in this case.
   - It should check whether the transaction can be completed now or it needs to be rolled back.
   - No transactions would be allowed to leave the DBMS in an inconsistent state.

