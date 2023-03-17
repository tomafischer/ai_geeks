# DAX 

## PowerBI links
[Embedding hyperlinks in tables:](https://docs.microsoft.com/en-us/power-bi/create-reports/power-bi-hyperlinks-in-tables)

[Hiding controls](https://exceleratorbi.com.au/show-or-hide-a-power-bi-visual-based-on-selection/)

## DAX Awesomeness
- DAX Formater : http://www.daxformatter.com/  
- DAX do online coder: http://dax.do  
- DAX patterns: https://www.daxpatterns.com/
- good best practise: https://help.zebrabi.com/article/90-star-schema
- Download earlier versions: https://docs.microsoft.com/en-us/power-bi/fundamentals/desktop-latest-update-archive?tabs=powerbi-desktop#november-2020-update-2872610 

## Measures for Colors:
```python
VAR _days_ahead =
    FIRSTNONBLANK ( 'Orders'[Age_in_Days], 0 )
VAR _color =
    SWITCH (
        TRUE,
        ISBLANK(_days_ahead), "rgba(255, 255, 143,0.8)" , // canary yellow
        _days_ahead < 0, "rgba(255,100,100,0.8)", //light red
        _days_ahead < 31, "rgba(255,165,0,0.8)", //orange
        _days_ahead < 91, "rgba(0,255,0,0.3)",  //green
        "rgba(182, 208, 226,0.8)" // light steel blue
    )
RETURN
    _color

```




## Report Builder
 - [Using cascading or equal paramters in Report Builder. Really got explanations](https://onyxdata.co.uk/microsoft-power-bi-uk-user-group-webinar-paginated-reports-with-parvinder-chana/)
