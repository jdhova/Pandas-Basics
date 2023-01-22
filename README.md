## PADAS notes

### Pandas is a python Data Library which is used in convarting data types to tables

#### Pandas puts Dictionaries into tables and pairs them accoring to their key and value pairs
```
import pandas as pd

a = [1, 7, 2]

myvar = pd.Series(a)

print(myvar)
 
 will output  ==>

    cars  quantity  models
0    BMW         3    2013
1  Volvo         7    2017
2   Ford         2    2012

print(df.loc[0]) // returns index 0
 
```
#### Pandas Puts Arrays and into series 
```

a = [['james','adam','joe','dave'],[1, 7, 2,3],[10,20,30,40]]

myvar = pd.Series(a)

print(myvar)

```
#### Bulding table with Pandas and finding the index and with Numpy

```

import pandas as pd
import numpy as np

a = [['james','adam','joe','dave'],[1, 7, 2,3],[10,20,30,40]]

myvar = pd.Series(a)

# print('withpandas',myvar[0,2]) will fail because pandas just build tables

myvars = np.array([myvar])

print('withnumpy',myvars)
print('withnumpy',myvars[0,2])



```
#### Creating Table Keys PF and FK with Pandas
```

import pandas as pd

a = [1, 7, 2]

myvar = pd.Series(a, index = ["x", "y", "z"])

print(myvar)


```

### CLEANING DATA
### Pandas can also load data from csv and have it imported for cleaning.

```

import pandas as pd

df = pd.read_csv('data.csv')

print(df) 

print(pd.options.display.max_rows)  this shows max rows

pd.options.display.max_rows = 9999 this sets how many rows to return

```

#### removing date rows 
```
import pandas as pd

df = pd.read_csv('data.csv')

df['Date'] = pd.to_datetime(df['Date'])

df.dropna(subset=['Date'], inplace = True)

print(df.to_string())


```

#### Replacin values N/A in claories with 130
```
import pandas as pd

df = pd.read_csv('data.csv')

df["Calories"].fillna(130, inplace = True)

```
#### Replacing value witht he mode median and mean

```
import pandas as pd

df = pd.read_csv('data.csv')

x = df["Calories"].mean()

df["Calories"].fillna(x, inplace = True)

```

#### Looping tru and changing the values of Index to 120 or a particular value
```
import pandas as pd

df = pd.read_csv('data.csv')

for x in df.index:
  if df.loc[x, "Duration"] > 120:
    df.loc[x, "Duration"] = 120

print(df.to_string())

```
#### Removing Duplicates

```
import pandas as pd

df = pd.read_csv('data.csv')

df.drop_duplicates(inplace = True)

print(df.to_string())

```

