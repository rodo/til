Fire the trigger only if something has changed in the tuple
===========================================================
    
```sql
    CREATE TRIGGER es_update_article
        AFTER UPDATE OF title, content ON articles
        FOR EACH ROW
        WHEN (OLD.* IS DISTINCT FROM NEW.*)
        EXECUTE PROCEDURE reindex_article();
    ```

Thanks to https://github.com/Mikulas/pg-es-fdw

Ref : http://www.postgresql.org/docs/current/static/sql-createtrigger.html