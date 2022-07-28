<div class="top">

# Unloading and counting
### [◂](command:katapod.loadPage?step6){.steps} Step 7 of 7 [▸](command:katapod.loadPage?finish){.steps}
</div>

Finally, take a look at how commands `unload` and `count` can be used to 
export data from Cassandra and compute simple row counts. 

Unload all rows from table `ratings_by_movie`:
```
dsbulk unload -url all_ratings    \
              -k killr_video      \
              -t ratings_by_movie \
              -header true        \
              -logDir /tmp/logs 
```

Unload rows from table `ratings_by_movie` using a query:
```
dsbulk unload -url m267_ratings   \
              -query "            \
SELECT *                          \
FROM killr_video.ratings_by_movie \
WHERE movie_id = 'm267'"          \
              -header true        \
              -logDir /tmp/logs 
```

Check the resulting CSV files:
```
head -n 5 all_ratings/*
head -n 5 m267_ratings/*
```

Count all rows in table `ratings_by_movie`:
```
dsbulk count  -k killr_video      \
              -t ratings_by_movie \
              -logDir /tmp/logs 
```

Count rows in table `ratings_by_movie` using a query:
```
dsbulk count  -query "            \
SELECT *                          \
FROM killr_video.ratings_by_movie \
WHERE movie_id = 'm267'"          \
              -logDir /tmp/logs 
```

[continue](command:katapod.loadPage?finish){.orange_bar}
