<div class="top">

# Loading users
### [◂](command:katapod.loadPage?step3){.steps} Step 4 of 7 [▸](command:katapod.loadPage?step5){.steps}
</div>

Our first task is to load user data from file `users.csv` with header fields `user_id`, `gender` and `age` 
into table `users` with columns `id`, `gender` and `age`. 

Output the first five lines from the file:
```
head -n 5 users.csv
```

Verify that the table is empty:
```
cqlsh -e "SELECT * FROM killr_video.users LIMIT 5;"
```

Since the file field names and the table column names do no match exactly, 
we have to map fields to columns explicitly. There 
are many ways to do this as we demonstrate in the following examples.

Load data (name-to-name mapping):
```
dsbulk load -url assets/users.csv       \
            -k killr_video       \
            -t users             \
            -header true         \
            -m "user_id=id,      \
                gender=gender,   \
                age=age"         \
            -logDir /tmp/logs
```

Load data (position-to-name mapping): 
```
dsbulk load -url assets/users.csv       \
            -k killr_video       \
            -t users             \
            -header true         \
            -m "0=id,            \
                1=gender,        \
                2=age"           \
            -logDir /tmp/logs
```

Load data (skip the file header and specify the column names): 
```
dsbulk load -url assets/users.csv       \
            -k killr_video       \
            -t users             \
            -header false        \
            -skipRecords 1       \
            -m "id, gender, age" \
            -logDir /tmp/logs
```

Output five rows from the table:
```
cqlsh -e "SELECT * FROM killr_video.users LIMIT 5;"
```

[continue](command:katapod.loadPage?step5){.orange_bar}