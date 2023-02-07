# Power Automate snippets

## Dealing with empty values
```python
# empty function - be aware that empty([]) will return false
if(empty(items('Apply_to_each')?['Activity Start']), null, items('Apply_to_each')?['Activity Start'])
```

use of length function might be better sometimes, 
```
if(equals(length(items('Apply_to_each')?['Activity Start']),0), 
   null, 
   items('Apply_to_each')?['Activity Start']
  )
```
## Excel
[Date Time explained](https://www.myonlinetraininghub.com/excel-date-and-time)
### DateTime conversions
```python
# from Excel float to minute precision
if(empty(items('Apply_to_each')?['Review Date']), 
   null, 
   convertTimeZone(string(addMinutes('1899-12-30 00:00:00', 
                   int(first(split(string(mul(float(items('Apply_to_each')?['Review Date']),1440)),'.'))))), 
                  'Eastern Standard Time', 'UTC')
)

## from Excel float to second precision
if(empty(items('Apply_to_each')?['Review Date']), 
   null, 
   convertTimeZone(string(addSeconds('1899-12-30 00:00:00', 
                                     int(first(split(string(mul(float(items('Apply_to_each')?['Review Date']),86400 )),'.'))))), 
                 'Eastern Standard Time', 
                 'UTC')
 )
 ```
