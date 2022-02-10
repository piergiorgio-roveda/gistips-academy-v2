# Create code from seq

```sql
UPDATE table1
SET
item_token=md5(pid::text||(now())::text)
code='UU' || LPAD(pid::text,10,'0')
-- note: SERIAL type is 4 bytes (1 to 2,147,483,647)
	
	
ALTER TABLE table1
ALTER COLUMN code 
    SET DEFAULT 'UU' || LPAD(
        (currval('table1_pid_seq'::regclass) + 1)::text,
        10,
        '0'
    );

ALTER TABLE table1
ALTER COLUMN item_token 
    SET DEFAULT md5(
        (currval('table1_pid_seq'::regclass) + 1)::text
            ||'-'||
            (now())::text
    );
```
