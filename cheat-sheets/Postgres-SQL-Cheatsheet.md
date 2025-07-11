# Postgres SQL Cheatsheet

## Table of Contents

- [Connecting](#connecting)
- [Basic Commands](#basic-commands)
- [Table Operations](#table-operations)
- [Query Examples](#query-examples)
- [Useful Functions](#useful-functions)
- [Indexes](#indexes)
- [Add users and manage permissions](#add-users-and-manage-permissions)
  - [Users](#users)
  - [Permissions](#permissions)
- [BACKUPS](#backups)
  - [Create backup](#create-backup)
  - [Restore backup](#restore-backup)

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
    name VARCHAR(100) NOT NULL,
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

## Add users and manage permissions

### Users

```sql
-- Create User --
CREATE USER <user_name> WITH PASSWORD '<password>';

-- Drop (Delete) User --
DROP USER IF EXISTS <user_name>;

-- Alter User Passwords --
ALTER ROLE <user_name> WITH PASSWORD '<password>';
```

### Permissions

```sql
-- Grant ALL  permissions on database --
GRANT ALL PRIVILEGES ON DATABASE <db_name> TO <user_name>;

-- Grant connection to select on table --
GRANT SELECT ON ALL TABLES IN SCHEMA public TO <username>;

-- Grant permissions on on all tables of db --
GRANT SELECT, UPDATE, INSERT ON ALL TABLES IN SCHEMA public TO <user_name>;
```

## BACKUPS

### Create backup

```shell
pg_dump -d <db_name> -f <filename>.sql
```

### Restore backup

```psql
psql -U user mydb < mydb_backup.sql
```
