# Postgres SQL Cheatsheet

## Connecting

```sh
psql -U username -d dbname
```

## Basic Commands

| Command | Description |
|---|---|
| `\l` | List databases |
| `\c dbname` | Connect to database |
| `\dt` | List tables |
| `\d tablename` | Describe table |
| `\q` | Quit psql |

## Table Operations

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name TEXT NOT NULL,
    email TEXT UNIQUE
);

INSERT INTO users (name, email) VALUES ('Alice', 'alice@email.com');

SELECT * FROM users;

UPDATE users SET name = 'Bob' WHERE id = 1;

DELETE FROM users WHERE id = 1;
```

## Query Examples

```sql
SELECT * FROM users WHERE name LIKE 'A%';
SELECT COUNT(*) FROM users;
SELECT name, COUNT(*) FROM users GROUP BY name;
```

## Useful Functions

```sql
NOW();           -- Current timestamp
LOWER(text);     -- Lowercase
UPPER(text);     -- Uppercase
```

## Indexes

```sql
CREATE INDEX idx_name ON users(name);
```
