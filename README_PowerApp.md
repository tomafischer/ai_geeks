# Date Snippets
[build a time picker component](https://www.matthewdevaney.com/make-a-time-picker-in-power-apps/#:~:text=Using%20The%20Time%20Picker%20In%20An%20App&text=Add%20the%20Time%20Picker%20component,the%20text%20input%27s%20Default%20property.&text=Insert%20a%20new%20label%20onto%20the%20screen%20to%20act%20as%20an%20overlay.)
```python
## For Hours:
## For Gallery
Items: ForAll(Sequence(12), Text(Value,"[$-en-US]00"))
## or for a dropdown list
Set(var_hours, [Blank(),"00","01","02","03","04","05","06","07","08","09","10","11","12","13","14","15","16","17","18","19","20","21","22","23" ]);

```

```python
## Convert to UTC
DateAdd( ThisItem.End_DateTime , TimeZoneOffset(), Minutes )
```
