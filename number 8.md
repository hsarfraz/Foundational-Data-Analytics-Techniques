# R

```
# You can load libraries like dplyr if needed
library(dplyr)

# access your data
head(stores)

stores %>%
group_by(store_id, year) %>%
summarise(yearly_total = sum(revenue), .groups = "drop") %>%
group_by(store_id) %>%
summarise(average_yearly_revenue = round(mean(yearly_total),2)) %>%
filter(average_yearly_revenue > 1000000) %>%
arrange(store_id)
```

# Python

```
import pandas as pd;

stores.head()
yearly_avg_df = stores.groupby(['store_id', 'year'], as_index = False).agg(yearly_total = ('revenue', 'sum')).groupby('store_id', as_index = False).agg(yearly_avg = ('yearly_total','mean'))
yearly_avg_df['yearly_avg'] = yearly_avg_df['yearly_avg'].round(2)
yearly_avg_df.loc[ (yearly_avg_df['yearly_avg'] > 1000000),:]
```

# MySQL

```
SELECT store_id,
  ROUND(AVG(yearly_total), 2) AS yearly_average
FROM (
  SELECT store_id, year, 
  SUM(revenue) AS yearly_total
FROM stores
GROUP BY store_id, year
  ) t

GROUP BY store_id
HAVING AVG(yearly_total) > 1000000
ORDER BY store_id
```

# PostgresSQL

```
SELECT store_id,
  ROUND(AVG(yearly_total)::numeric, 2) AS yearly_avg
FROM (
  SELECT store_id,
  SUM(revenue) AS yearly_total
FROM stores
GROUP BY store_id, year
  ) t
GROUP BY store_id
HAVING ROUND(AVG(yearly_total)::numeric, 2) > 1000000
ORDER BY store_id ASC
```

# MSSQL

```
SELECT store_id,
  ROUND(AVG(CAST(yearly_total AS FLOAT)), 2) AS yearly_avg
FROM
  (
  SELECT store_id,
  SUM(revenue) AS yearly_total
FROM stores
GROUP BY store_id, year) t 
GROUP BY store_id 
HAVING ROUND(AVG(CAST(yearly_total AS FLOAT)), 2) > 1000000;
```
