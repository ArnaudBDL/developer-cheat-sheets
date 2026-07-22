# MySQL : Data Types

## Numeric Types

```sql
TINYINT
SMALLINT
INT
BIGINT
DECIMAL(12,2)
FLOAT
DOUBLE
```

## Text and Binary Types

```sql
CHAR(2)
VARCHAR(255)
TEXT
MEDIUMTEXT
BINARY(16)
VARBINARY(255)
BLOB
```

## Date and Time Types

```sql
DATE
TIME
DATETIME
TIMESTAMP
YEAR
```

## Other Types

```sql
BOOLEAN
ENUM('draft', 'published')
SET('read', 'write')
JSON
```

Use `DECIMAL` for exact fixed-point values such as money. Choose sizes and nullability according to the data domain.
