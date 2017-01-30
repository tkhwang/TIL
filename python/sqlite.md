# sqlite

```python
import sqlite3

conn = sqlite3.connect("./data/database.db")
cur = conn.cursor()
cur.execute("SELECT country FROM countries WHERE area >= 2000000")
rows = cur.fetchall()
conn.close()

for i in rows:
    print(i[0])
```

```python
import sqlite3
import pandas

conn = sqlite3.connect("./data/database90.db")
cur = conn.cursor()
cur.execute("SELECT * FROM countries WHERE area >= 2000000")
rows = cur.fetchall()
conn.close()

df = pandas.DataFrame.from_records(rows)
df.columns = ["Rank", "Country", "Area", "Population"]
df.to_csv("countries_big_area.csv", index=False)
```
