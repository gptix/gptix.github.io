---
layout: post
title: SQLite3 - Pandas Utilities
subtitle: Use tools for what they are good
---

# Simple SQLite3 Pandas Utilities

Pandas is a great tool for manipulating well-structured data.

SQLite3 is a way to store and retrieve data in a well-structured way.

I wrote some python to encapsulate common tasks in using SQLite3 and Pandas.

Might delete later.

```
import pandas as pd
import sqlite3

test_db_filename = 'starfleet_missions.sqlite3'

sqlite_conn = sqlite3.connect(test_db_filename)

sqlite_cursor = sqlite_conn.cursor()

# test query
test_sql = """
SELECT  DISTINCT  StarshipName, PlanetName, StarDate
FROM    Missions
        INNER JOIN Planets
            ON Planet.ID = Mission.PlanetID        
ORDER BY StarDate DESC
LIMIT 10"""
```


```
def descr_to_lst(d): 
    """Returns a list of names of columns retrieved from the description attribute of an SQLite3 cursor.  
    A Description is a list of 7-tuples.  Each first position
     holds a column's name.  The other six positions hold 
    a None."""
    return [i[0] for i in d]
```

```
def cursor_to_colnames(crsr):
    """Returns names of columns in a cursor object."""
    return descr_to_lst(crsr.description)

```

```
def sqlite_cursor_to_pandas_dataframe(crsr):
    """Given an sqlite3 cursor, return a Pandas DataFrame."""
    vs = np.array(crsr.fetchall())
    cls = cursor_colnames(crsr)
    return pd.DataFrame(data=vs, columns=cls)
```
```
def sql_to_df(sql, crsr=sqlite_cursor):
    """Execute an SQL statement on an sqlite3 cursor, then return a Pandas DataFrame."""
    crsr.execute(sql)
    return sqlite_cursor_to_pandas_dataframe(crsr)
```

```
def sql_statement_to_rslts(sql, crsr=sqlite_cursor):
    crsr.execute(sql)
    return sqlite_cursor_to_pandas_dataframe(crsr)
```
