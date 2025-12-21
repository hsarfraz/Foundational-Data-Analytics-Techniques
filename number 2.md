# R Programming

```
# You can load libraries like dplyr if needed
library(dplyr)

# access your data
head(web_traffic)

web_traffic %>%
 group_by(date_visited) %>%
 summarise(count = n_distinct(visitor_id)) %>%
  arrange(date_visited)
```

# Python

```
# access datasets as pandas dataframes
import pandas as pd;

web_traffic.head()

df_series = web_traffic.groupby('date_visited')['visitor_id'].nunique()
df = df_series.reset_index()
df.sort_values('date_visited')
```

# MySQL

```
SELECT date_visited, COUNT(DISTINCT visitor_id) AS visitor_id
FROM web_traffic
GROUP BY date_visited
ORDER BY date_visited ASC
```

# PostgresSQL

```
SELECT date_visited, COUNT(DISTINCT visitor_id) AS visitor_id
FROM web_traffic
GROUP BY date_visited
ORDER BY date_visited
```

# MSSQL

```
SELECT date_visited, COUNT(DISTINCT visitor_id) AS visitor_id
FROM web_traffic
GROUP BY date_visited
ORDER BY date_visited;
```
