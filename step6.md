<div class="top">

# Loading ratings
### [◂](command:katapod.loadPage?step5){.steps} Step 6 of 7 [▸](command:katapod.loadPage?step7){.steps}
</div>

Let's load movie ratings from file `ratings.csv` 
into tables `ratings_by_user` and `ratings_by_movie`. 

Output the first five lines from the file:
```
head -n 5 ratings.csv
```

Verify that the tables are empty:
```
cqlsh -e "SELECT * FROM killr_video.ratings_by_user LIMIT 5;"
cqlsh -e "SELECT * FROM killr_video.ratings_by_movie LIMIT 5;"
```

Notice that the file field names and the table column names match. We do not 
need to provide an explicit mapping this time.

Load data into table `ratings_by_user`:
```
dsbulk load -url ratings.csv      \
            -k killr_video        \
            -t ratings_by_user    \
            -header true          \
            -logDir /tmp/logs
```

Load data into table `ratings_by_movie`:
<details>
  <summary>Solution</summary>

```
dsbulk load -url ratings.csv      \
            -k killr_video        \
            -t ratings_by_movie   \
            -header true          \
            -logDir /tmp/logs
```

</details>

Output five rows from each table:
```
cqlsh -e "SELECT * FROM killr_video.ratings_by_user LIMIT 5;"
cqlsh -e "SELECT * FROM killr_video.ratings_by_movie LIMIT 5;"
```

[continue](command:katapod.loadPage?step7){.orange_bar}