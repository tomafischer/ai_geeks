# Power Automate snippets

## Dealing with empty values
```python
# empty function - be aware that empty([]) will return false
if(empty(items('Apply_to_each')?['Activity Start']), null, items('Apply_to_each')?['Activity Start'])
```

use of length function might be better sometimes, 
```python
if(equals(length(items('Apply_to_each')?['Activity Start']),0), 
   null, 
   items('Apply_to_each')?['Activity Start']
  )

# check variables for null (note this is the actual name not the header name)
if(empty(variables('end_date')),
   null,
   variables('end_date')
   )
```

## Trigger user name
```python
triggerOutputs()['headers']['x-ms-user-name']
```
## Excel
[Date Time explained](https://www.myonlinetraininghub.com/excel-date-and-time)

[Date parsing/formating explained](https://barretblake.dev/2022/08/function-friday-formatting-and-parsing-dates-and-times/?utm_source=rss&utm_medium=rss&utm_campaign=function-friday-formatting-and-parsing-dates-and-times)

[Reading a long excel table]([https://learntoilluminate.com/2022/07/power-automate-retrieve-more-than-5000-records-from-dataverse-or-dynamics-365-ce-crm/#:~:text=Using%20Power%20Automate%2C%20We%20can,total%20count%20is%2010139%20records.](https://learntoilluminate.com/2023/01/power-automate-retrieve-over-5000-records-from-dataverse-or-dynamics-365-ce-crm-and-create-csv-file/))
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
 
 addSeconds: 
 -> "1900-02-14T07:06:40.0000000"
 convertTimezone to UTC
 -> "2022-09-22T14:00:00.0000000Z"
 
# Parsing 12/20/21A and regular dates mixed 
if(empty(items('Apply_to_each')?['Start Date']), 
   null ,
   if(not(contains(items('Apply_to_each')?['Start Date'], '/')),
        convertTimeZone(string(addSeconds('1899-12-30 00:00:00', 
                                        int(first(split(string(mul(float(items('Apply_to_each')?['Start Date']),86400 )),'.'))))), 
                                        'Eastern Standard Time', 
                                        'UTC'
                        ),
      if(greater(nthIndexOf(items('Apply_to_each')?['Start Date'],'A',1), -1), 
         parseDateTime(slice(items('Apply_to_each')?['Start Date'], 0, add(nthIndexOf(items('Apply_to_each')?['Start Date'], '/', 2), 3)),  'en-US'),
         parseDateTime(items('Apply_to_each')?['Start Date'], 'en-US')
        )
     )
 )
