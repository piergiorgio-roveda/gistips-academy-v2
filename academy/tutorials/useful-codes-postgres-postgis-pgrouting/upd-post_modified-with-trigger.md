# UPD post\_modified with Trigger

```sql
DROP FUNCTION IF EXISTS public.fwd_update_twitter_user();

CREATE OR REPLACE FUNCTION public.fwd_update_twitter_user()
    RETURNS trigger
    LANGUAGE 'plpgsql'
    COST 100
    VOLATILE NOT LEAKPROOF
AS $BODY$
    BEGIN
        UPDATE twitter_user
			SET 
				post_modified = now()
		WHERE pid = NEW.pid;
        RETURN NEW;
    END;
$BODY$;

CREATE TRIGGER tgeo_update_twitter_user
    AFTER UPDATE
    ON public.twitter_user
    FOR EACH ROW
    EXECUTE PROCEDURE public.fwd_update_twitter_user();
```
