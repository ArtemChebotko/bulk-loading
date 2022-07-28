<div class="top">

# Loading movies
### [◂](command:katapod.loadPage?step4){.steps} Step 5 of 7 [▸](command:katapod.loadPage?step6){.steps}
</div>

Next, load movie data from file `movies.csv` 
into table `movies`. 

Output the first five lines from the file:
```
head -n 5 assets/movies.csv
```

Verify that the table is empty:
```
cqlsh -e "SELECT * FROM killr_video.movies LIMIT 5;"
```

Load data:
<details>
  <summary>Solution</summary>

```
dsbulk load -url assets/movies.csv \
            -k killr_video         \
            -t movies              \
            -header true           \
            -m "movie_id=id,       \
                title=title,       \
                year=year,         \
                duration=duration, \
                country=country"   \
            -logDir /tmp/logs
```

</details>

Output five rows from the table:
```
cqlsh -e "SELECT * FROM killr_video.movies LIMIT 5;"
```

[continue](command:katapod.loadPage?step6){.orange_bar}