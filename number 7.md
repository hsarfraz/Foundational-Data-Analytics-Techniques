# R

```
# You can load libraries like dplyr if needed
library(dplyr)

# access your data
head(bakery_items)

bakery_items[grepl('Chocolate', bakery_items$product_name), , drop=FALSE]
```

# Python

```
# access datasets as pandas dataframes
import pandas as pd;

bakery_items.head()
bakery_items.loc[ bakery_items['product_name'].str.contains('Chocolate'),:]
```

# MySQL

```
SELECT *
FROM bakery_items
WHERE product_name LIKE '%Chocolate%'
```

# PostgreSQL

```
SELECT *
FROM bakery_items
WHERE product_name LIKE '%Chocolate%'
```

# MSSQL

```
SELECT *
FROM bakery_items
WHERE product_name LIKE '%Chocolate%';
```
