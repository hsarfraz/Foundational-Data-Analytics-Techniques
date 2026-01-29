# R

```
# You can load libraries like dplyr if needed
library(dplyr)

# access your data
head(employee_name)
head(employee_location)
employee_location['person_id'] <- employee_location['employee_id']

full_join(employee_name, employee_location, by = "person_id") %>%
select(first_name, last_name, state) %>%
arrange(first_name)
```

# Python

```
# access datasets as pandas dataframes
import pandas as pd;

employee_name.head()

employee_location['person_id'] = employee_location['employee_id']
pd.merge(employee_name, employee_location, on='person_id', how='outer').loc[:,['first_name', 'last_name', 'state']].sort_values(by='first_name', ascending=True)
```

# MySQL

```
SELECT en.first_name, en.last_name, el.state
FROM employee_name en
LEFT JOIN employee_location el
ON en.person_id = el.employee_id

UNION

SELECT en.first_name, en.last_name, el.state
FROM employee_name en
RIGHT JOIN employee_location el
ON en.person_id = el.employee_id

ORDER BY first_name
```

# PostgresSQL

```
SELECT en.first_name, en.last_name, el.state 
FROM employee_name en 
LEFT JOIN employee_location el 
ON en.person_id = el.employee_id

UNION

SELECT en.first_name, en.last_name, el.state
FROM employee_name en 
RIGHT JOIN employee_location el 
ON en.person_id = el.employee_id 

ORDER BY first_name
```

# MSSQL

```
SELECT en.first_name, en.last_name, el.state 
FROM employee_name en 
LEFT JOIN employee_location el 
  ON en.person_id = el.employee_id 
  
UNION 
  
SELECT en.first_name, en.last_name, el.state 
FROM employee_name en 
RIGHT JOIN employee_location el 
  ON en.person_id = el.employee_id 

ORDER BY first_name;
```
