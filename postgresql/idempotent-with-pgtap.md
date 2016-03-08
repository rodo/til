Write idempotent script with pgTap internals
============================================
    
```sql
    --
    DO LANGUAGE plpgsql $$
    BEGIN

    IF _have_index(
        'namespace',
        'table_name',
        'index_name')
    THEN

      DROP INDEX index_name;

    END IF;

    END;
    $$;
```



Ref : https://github.com/theory/tap-parser-sourcehandler-pgtap