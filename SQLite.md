# SQLite

_SQLite is a C-language library that implements a small, fast, self-contained, high-reliability, full-featured, SQL database engine._

## SQLite and Node

`sqlite3`is a asynchronous (callback based), non-blocking SQLite3 bindings for Node.js.

[sqlite3](https://github.com/mapbox/node-sqlite3)

`db-migrate` is a database migration framework for node.js

_In software engineering, schema migration (also database migration, database change management) refers to the management of incremental, reversible changes and version control to relational database schemas. A schema migration is performed on a database whenever it is necessary to update or revert that database's schema to some newer or older version._

`db-migrate-sqlite3` is a sqlite driver for db-migrate

[db-migrate](https://github.com/db-migrate/node-db-migrate)
[db-migrate-sqlite3](https://github.com/db-migrate/sqlite)

## Data types

Each value stored in an SQLite database has one of the following storage classes:

| NULL    | The value is a NULL value.
| INTEGER | The value is a signed integer, stored in 1, 2, 3, 4, 6, or 8 bytes depending on the magnitude of the value.
| REAL    | The value is a floating point value, stored as an 8-byte IEEE floating point number.
| TEXT    | The value is a text string, stored using the database encoding (UTF-8, UTF-16BE or UTF-16LE).
| BLOB    | The value is a blob of data, stored exactly as it was input.

SQLite does not have a storage class set aside for storing dates and/or times.
Instead, the built-in Date And Time Functions of SQLite are capable of storing dates and times as TEXT, REAL, or INTEGER values:

| TEXT    | ISO8601 strings ("YYYY-MM-DD HH:MM:SS.SSS").
| REAL    | Julian day numbers, the number of days since noon in Greenwich on November 24, 4714 B.C. according to the proleptic Gregorian calendar.
| INTEGER | Unix Time, the number of seconds since 1970-01-01 00:00:00 UTC.

## Primary Key

The AUTOINCREMENT keyword imposes extra CPU, memory, disk space, and disk I/O overhead and should be avoided. It is usually not needed.

In SQLite, a column with type INTEGER PRIMARY KEY is an alias for the ROWID (except in WITHOUT ROWID tables) which is always a 64-bit signed integer.

### db-migrate support

[Supported db-migrate data types](https://github.com/db-migrate/shared/blob/master/data_type.js)

- CHAR: 'char',
- STRING: 'string',
- TEXT: 'text',
- SMALLINT: 'smallint',
- BIGINT: 'bigint',
- INTEGER: 'int',
- SMALL_INTEGER: 'smallint',
- BIG_INTEGER: 'bigint',
- REAL: 'real',
- DATE: 'date',
- DATE_TIME: 'datetime',
- TIME: 'time',
- BLOB: 'blob',
- TIMESTAMP: 'timestamp',
- BINARY: 'binary',
- BOOLEAN: 'boolean',
- DECIMAL: 'decimal'

The following options are available on column specs

- type: the column data type.
- length: the column data length, where supported
- primaryKey: true to set the column as a primary key (can be setted on multiple columns)
- autoIncrement: true to mark the column as auto incrementing
- notNull: true to mark the column as non-nullable
- unique: true to add unique constraint to the column
- defaultValue: set the column default value.
  - To set an expression (eg a function call) as the default value use this syntax: defaultValue: new String('uuid_generate_v4()')
- foreignKey: set a foreign key to the column

## Date and Time functions

[Date And Time Functions](https://www.sqlite.org/lang_datefunc.html)

SQLite supports date and time functions as follows:

- date(time-value, modifier, modifier, ...) => returns the date in this format: YYYY-MM-DD
  -> date('now')
  -> date('now','start of month','+1 month','-1 day')

- time(time-value, modifier, modifier, ...) => returns the time as HH:MM:SS
  -> date('now', '-1 hour')

- datetime(time-value, modifier, modifier, ...) => returns "YYYY-MM-DD HH:MM:SS"
  -> datetime('now','localtime')

- strftime(format, time-value, modifier, modifier, ...) => returns the date formatted according to the format string
  - strftime('%Y-%m-%d', ...)
  - strftime('%H:%M:%S', ...)
  - strftime('%Y-%m-%d %H:%M:%S', ...)

Valid time values:
- YYYY-MM-DD
- YYYY-MM-DD HH:MM:SS.SSS
- YYYY-MM-DDTHH:MM:SS.SSS (ISO-8601)
- now

[SQLite dates and JavaScript formatting](https://www.sitekickr.com/blog/sqlite-javascript-date/)