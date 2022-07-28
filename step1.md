<div class="top">

# DataStax Bulk Loader
### [◂](command:katapod.loadPage?intro){.steps} Step 1 of 7 [▸](command:katapod.loadPage?step2){.steps}
</div>

DataStax Bulk Loader (DSBulk) is an efficient, flexible, easy-to-use and free command-line utility for Apache Cassandra™ 
that excels at loading, unloading and counting data. You should use DSBulk to:

- Load data from CSV or JSON files into the database
- Unload data stored in the database into CSV or JSON files
- Quickly count the number of rows in a given table

DSBulk is a good choice for small, medium and large datasets. It gets data in and out of the database 
significantly faster than individual `INSERT`s, the `COPY` command or other community tools. Only for very large datasets 
that reside in a distributed file system, a potentially faster alternative to DSBulk 
could be data loading with Apache Spark™.

[continue](command:katapod.loadPage?step2){.orange_bar}