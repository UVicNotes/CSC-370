# Introduction

## What is a database?

__definition:__ A **database** is a collection of information that exists over a long period of time.

A **Database Management System (DBMS)** a complex system for managing database interactions.

1. Allows users to *easily* create new databases and specify schema.
1. Enables users for *search* and *modify* data.
1. Stores data *intelligently*,
	* Protects from accidental use
	* Allows efficient access, e.g., indexing
1. Manages *cuncurrent* data accesses and modifications.
1. Recovers from failures and crashes.

## Relational Databases

A database system should present the user with a view of the data organized as *tables* (or *relations*).

So `Relations` are represented as `Tables`, column headers are *attribute names*. Each row is a *tuple*.

Access with **Structured Query Language (SQL)**.

##### e.g.

Given the database

| `accountNo` | `balance` | `type` |
|:-:|:-:|:-:|
| 12345 | 1000.00 | `savings` |
| 67890 | 2846.92 | `checking` |
| ... | ... | ... |

1. What’s the balance of account “67890”?

```sql
SELECT balance
FROM Accounts
WHERE accountNo = 67890;
```

2. Which are the savings accounts with negative balances?

```sql
SELECT accountNo
FROM Accounts
WHERE type = ‘savings’ AND balance < 0;
```
