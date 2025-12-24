# R

```
# You can load libraries like dplyr if needed
library(dplyr)

# access your data
head(employees)
employees$birth_date <- as.Date(employees$birth_date, format = "%m/%d/%Y")
df <- employees[ order(employees$birth_date) , ]
#df$birth_date <- format(df$birth_date, '%m/%d/%Y') #to change datetime column from integer to date
head(df[,'employee_id', drop=FALSE],3)
```

# Python

```
# access datasets as pandas dataframes
import pandas as pd;

employees['birth_date'] = pd.to_datetime(employees['birth_date'], format='%m/%d/%Y')
df_sorted = employees.sort_values(by='birth_date', ascending=True)
df_sorted.loc[:,['employee_id']].head(3)
```

# SQL

```
SELECT employee_id
FROM employees
ORDER BY birth_date
LIMIT 3;
```

# PostgresSQL

```
SELECT employee_id
FROM employees
ORDER BY birth_date ASC
LIMIT 3;
```

# MSSQL

```
SELECT TOP 3 employee_id
FROM employees
ORDER BY birth_date;
```
