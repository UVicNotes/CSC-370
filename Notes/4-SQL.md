# Structured Query Language (SQL)

**Strutured Query Language (SQL)**, [often prounounced "Sequel"](http://english.stackexchange.com/questions/7231/how-is-sql-pronounced), is a programming language for manipulating databases.


## SQL Common Data Types

| Data type | Description |
|---|---|
| `CHARACTER(n)` | Character string. Fixed-length `n`. |
| `VARCHAR(n)` | Character string. Variable length. Maximum length `n`. |
| `BINARY(n)` | Binary string. Fixed-length `n`. |
| `BOOLEAN` | Stores `TRUE` or `FALSE` values. |
| `VARBINARY(n)` | Binary string. Variable length. Maximum length `n`. |
| `INTEGER(p)` | Integer numerical (no decimal). Precision `p`. |
| `DATE` | Stores year, month, and day values. |
| `TIME` | Stores hour, minute, and second values. |
| `TIMESTAMP` | Stores year, month, day, hour, minute, and second values. |
| `ARRAY` | A set-length and ordered collection of elements. |
| `MULTISET` | A variable-length and unordered collection of elements. |
| `XML` | Stores XML data. |

## Creating Tables

We can create a table with the `CREATE` command

```sql
CREATE TABLE Studios(
  name VARCHAR(20),
  website VARCHAR(255)
);
```

### Creating with Primary Keys

To assign a single primary Keys

```sql
CREATE TABLE Studios(
  name VARCHAR(20) PRIMARY KEY,
  website VARCHAR(255)
);
```

To assign multiple primary Keys

```sql
CREATE TABLE Movies (
  title VARCHAR(50),
  year INT,
  length INT,
  rating CHAR(2),
  studioname VARCHAR(20),
  PRIMARY KEY (title, year)
);
```

