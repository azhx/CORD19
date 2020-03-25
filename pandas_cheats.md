#  __Useful Pandas functions you may have been looking for__

# NaN Check
```py
val != val
``` 
(evaluates to true when NaN because NaN does not equal itself)

# write csv without indices
```py
df.to_csv('name.csv', index = False)
```

# count each unique value in a column
```py
df['col'].value_counts()
```

# count non-NaN values in every column
```py
df.info()
```

# drop rows with NAN or NAT in a column
```py
df.dropna(subset=['col'])
```


# get row based on  index
```py
df.iloc[i]
```

# get rows with value in a column
```py
df.query('colname == val')
``` 
or 
```py
df[df.colname == val]
```

# clean column names so you can access by `df.query`

```py
df.columns = df.columns.str.strip().str.lower().str.replace(' ', '_').str.replace('(', '').str.replace(')', '')
```

for a more comprehensive method using regex:

```py
import re
df.columns = [re.sub(r'[ /?+@()%#]', '_', x.lower().strip() for x in df.columns]
```
