<div class="top">

# Let's get started ...
### [◂](command:katapod.loadPage?step2){.steps} Step 3 of 7 [▸](command:katapod.loadPage?step4){.steps}
</div>

Create the keyspace and four tables using the CQL shell:
```
cqlsh -e "

CREATE KEYSPACE killr_video
WITH replication = {
  'class': 'NetworkTopologyStrategy', 
  'DC-Houston': 1 };

USE killr_video;

CREATE TABLE users (
  id TEXT,
  gender TEXT,
  age INT,
  PRIMARY KEY ((id))
);

CREATE TABLE movies (
  id TEXT,
  title TEXT,
  year INT,
  duration INT,
  country TEXT,
  PRIMARY KEY ((id))
);

CREATE TABLE ratings_by_user (
  user_id TEXT,
  movie_id TEXT,
  rating INT,
  PRIMARY KEY ((user_id), movie_id)
);

CREATE TABLE ratings_by_movie (
  movie_id TEXT,
  user_id TEXT,
  rating INT,
  PRIMARY KEY ((movie_id), user_id)
);"
```

[continue](command:katapod.loadPage?step4){.orange_bar}