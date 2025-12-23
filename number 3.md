# R

```
# You can load libraries like dplyr if needed
library(dplyr)

# access your data
head(bread_table)
head(meat_table)

df <- merge(bread_table,meat_table)
df[ order(df$bread_name, df$meat_name), c('bread_name','meat_name')]
```

# Python

```
# access datasets as pandas dataframes
import pandas as pd;

bread_table.head()
df = pd.merge(bread_table, meat_table, how='cross')
df.loc[:, ['bread_name','meat_name'] ].sort_values(['bread_name', 'meat_name'])
```

# MySQL

```
SELECT bread_name, meat_name
FROM bread_table
CROSS JOIN meat_table
ORDER BY bread_name, meat_name ASC
```

# PostgresSQL

```
SELECT bread_name, meat_name
FROM bread_table
CROSS JOIN meat_table
ORDER BY bread_name, meat_name ASC
```

# MSSQL

```
SELECT bread_name, meat_name
FROM bread_table
CROSS JOIN meat_table
ORDER BY bread_name, meat_name;
```
