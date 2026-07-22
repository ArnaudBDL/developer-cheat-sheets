# PostgreSQL : Data Types

## Common Types

```text
SMALLINT  INTEGER  BIGINT
NUMERIC(p,s)  REAL  DOUBLE PRECISION
BOOLEAN
CHAR(n)  VARCHAR(n)  TEXT
DATE  TIME  TIMESTAMP  TIMESTAMPTZ  INTERVAL
UUID  JSON  JSONB  BYTEA
ARRAY  RANGE  ENUM
```

## Examples

```sql
CREATE TABLE records (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  metadata JSONB NOT NULL DEFAULT '{}'::jsonb,
  tags TEXT[] NOT NULL DEFAULT '{}',
  valid_during TSTZRANGE
);
```

