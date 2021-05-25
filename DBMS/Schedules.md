# Schedule

- A chronological execution sequence of a transaction is called a schedule. A schedule can have many transactions in it, each comprising of a number of instructions/tasks.

  - ## Serial Schedule
    - It is a schedule in which transactions are aligned in such a way that one transaction is executed first. When the first transaction completes its cycle, then the next transaction is executed. Transactions are ordered one after the other.
  - ## Strict Schedule
    - Neither Dirty read nor Lost Update problem allowed, means reading or writing the data written by an uncommitted transaction is not allowed.
  - ## Cascadeless Schedule
    - Dirty Read not allowed, means reading the data written by an uncommitted transaction is not allowed. Lost Update problem may occur.
  - ## Recoverable Schedule
    - Transactions must be committed in order. Dirty Read problem and Lost Update problem may occur.


<br>
---
<br>

