# Table function
## Create Table from Record
```python
 Table.FromRecords({
        [CustomerID = 1, price = 20],
        [CustomerID = 2, price = 10],
        [CustomerID = 2, price = 20],
        [CustomerID = 1, price = 10],
        [CustomerID = 3, price = 20],
        [CustomerID = 3, price = 5]
    })
```
## Group table with agregates
```python
Table.Group(#"Renamed Columns", {"Id","RequestorId", "ContactAdminId", "PlannedDepartureLocation"}, {{"PassengerTitles", each Text.Combine([PassengerTitle],"; "), type text}, {"PassengerCount", each List.Count([PassengerTitle]), type number}})
```

