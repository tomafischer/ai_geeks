# SQL
## Timezone conversion
```sql
UPDATE dbo.tablename
SET CSTTimeStamp = cast( GMTTimeStamp at time zone 'UTC' at time zone 'CENTRAL STANDARD TIME' as datetime),
```
## Temp conversion
```
Temp_F = (Temp_C * 9/5) + 32
```
