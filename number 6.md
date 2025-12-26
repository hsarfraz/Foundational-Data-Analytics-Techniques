# R

```
# You can load libraries like dplyr if needed
library(dplyr)

# access your data
head(animals_secondary)
#head(animals_main)
df <- rbind(animals_main, animals_secondary)
df[ order(df$animal) ,]
```

# Python

```
import pandas as pd;

animals_secondary.head()

pd.concat( [animals_main, animals_secondary] , axis=0 ).sort_values('animal', ascending = True)
```

# MySQL

```
SELECT *
FROM animals_secondary
UNION ALL
SELECT *
FROM animals_main
ORDER BY animal ASC;
```

# PostgresSQL

```
SELECT *
FROM animals_secondary
UNION ALL
SELECT *
FROM animals_main
ORDER BY animal;
```

# MSSQL

```
SELECT *
FROM animals_secondary
UNION ALL
SELECT *
FROM animals_main
ORDER BY animal;
```
