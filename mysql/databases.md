# MySQL : Databases

## Create and Select

```sql
CREATE DATABASE application
  CHARACTER SET utf8mb4
  COLLATE utf8mb4_0900_ai_ci;

USE application;
SELECT DATABASE();
```

## Inspect

```sql
SHOW DATABASES;
SHOW CREATE DATABASE application;
SELECT schema_name, default_character_set_name
FROM information_schema.schemata;
```

## Modify and Drop

```sql
ALTER DATABASE application CHARACTER SET utf8mb4;
DROP DATABASE IF EXISTS application;
```
