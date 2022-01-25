## Create compound key from composit key
```
Date.ToText([t0_start],"yyyy_MM_dd")  & "__" &Number.ToText([total_weeks_ahead])& "_" & Number.ToText([tx])
or in advanced editor
#"Added Custom" = Table.AddColumn(#"Changed Type", "Add compound key", each Date.ToText([t0_start],"yyyy_MM_dd")  & "__" &Number.ToText([total_weeks_ahead])& "_" & Number.ToText([tx]))
```
