# SQL AGENTS

## Do

- SQL use lowercase

  ```sql
  begin;

  -- remove the supabase_realtime publication
  drop
      publication if exists supabase_realtime;
  
  -- re-create the supabase_realtime publication with no tables
  create publication supabase_realtime;
  
  commit;
  
  -- add a table called 'messages' to the publication
  -- (update this to match your tables)
  alter
      publication supabase_realtime add table messages;
  ```

## Don't

- Don't run db **reset**
- Don't use `ILIKE` for text search, use Postgres built-in functions to handle `Full Text Search` queries

  ```sql
    select
      *
    from
      books
    where
      to_tsvector(description || ' ' || title) -- concat columns, but be sure to include a space to separate them!
      @@ to_tsquery('little');
  ```

