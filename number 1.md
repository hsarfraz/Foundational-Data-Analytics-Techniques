# R Programming

```
# You can load libraries like dplyr if needed
library(dplyr)

# access your data
head(players)

skill_level <- ifelse(players$batting_average >= 0.38, 'Great Hitter', "Below Average")
players$skill_level <- ifelse(players$batting_average >= 0.27 &
                              players$batting_average <= 0.37,
                              'Average', skill_level)
players
```

# Python

* `and` used in scalar logic
* `&` used in series logic

```
# access datasets as pandas dataframes
import pandas as pd;

players.head()

players['skill_level'] = 'Below Average'
players.loc[players['batting_average'] >= 0.38 , 'skill_level'] = 'Great Hitter' #.loc converts to series
players.loc[(players['batting_average'] >= 0.27) & (players['batting_average'] <= 0.37), 
              'skill_level'] = 'Average'
players
```

# MySQL

SQL Clause Order

1. SELECT
2. FROM
3. JOIN
4. WHERE
5. GROUP BY
6. HAVING
7. ORDER BY
8. LIMIT

```
SELECT *,
  CASE
  WHEN batting_average > 0.37 THEN 'Great Hitter'
  WHEN batting_average >= 0.27 THEN 'Average'
  ELSE 'Below Average'
  END AS skill_level
FROM players
```

# PostgresSQL

```
SELECT *,
  CASE
  WHEN batting_average > 0.37 THEN 'Great Hitter'
  WHEN batting_average >= 0.27 THEN 'Average'
  ELSE 'Below Average'
  END AS skill_level
FROM players
```

# MSSQL

```
SELECT *,
  CASE
  WHEN batting_average > 0.37 THEN 'Great Hitter'
  WHEN batting_average >= 0.27 THEN 'Average'
  ELSE 'Below Average'
  END AS skill_level
FROM players;
```
