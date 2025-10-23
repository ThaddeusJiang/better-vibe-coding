# PostgreSQL rules

- Do **not** use `LIKE` operators! use Postgres built-in `Full Text Search` Queries.
- Do **not** use the Postgres `UUID` type, use `String` type ID instead.
