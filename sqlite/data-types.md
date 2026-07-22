# SQLite : Data Types

## Storage Classes

```text
NULL     Missing value
INTEGER  Signed integer
REAL     Floating-point value
TEXT     Text string
BLOB     Binary data
```

## Type Affinities

```text
INTEGER
TEXT
BLOB
REAL
NUMERIC
```

SQLite normally associates the storage class with the value. Column declarations provide type affinity rather than rigid typing unless the table is declared `STRICT`.

## Inspect Values

```sql
SELECT typeof(NULL);
SELECT typeof(42);
SELECT typeof(19.95);
SELECT typeof('SQLite');
SELECT typeof(X'53514C697465');
```

## Dates and Times

```sql
SELECT date('now');
SELECT time('now');
SELECT datetime('now');
SELECT unixepoch('now');
SELECT strftime('%Y-%m-%d', 'now');
```

## Boolean Values

```sql
CREATE TABLE features (
    enabled INTEGER NOT NULL CHECK (enabled IN (0, 1))
);
```

## JSON

```sql
SELECT json_extract(document, '$.name')
FROM records;
```
