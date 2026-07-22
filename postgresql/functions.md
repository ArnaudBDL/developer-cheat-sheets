# PostgreSQL : Functions

## SQL Function

```sql
CREATE FUNCTION add_numbers(left_value integer, right_value integer)
RETURNS integer
LANGUAGE sql
IMMUTABLE
RETURN left_value + right_value;
```

## PL/pgSQL Function

```sql
CREATE FUNCTION deactivate_user(user_id bigint) RETURNS void
LANGUAGE plpgsql AS $$
BEGIN
  UPDATE users SET active = FALSE WHERE id = user_id;
END;
$$;
```

## Inspect and Drop

```sql
\df+
SELECT add_numbers(2, 3);
DROP FUNCTION add_numbers(integer, integer);
```

