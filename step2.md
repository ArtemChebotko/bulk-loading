<div class="top">

# DSBulk commands and options
### [◂](command:katapod.loadPage?step1){.steps} Step 2 of 7 [▸](command:katapod.loadPage?step3){.steps}
</div>

DSBulk usage:
<pre style="color: #a31516">
dsbulk <command> [options]
</pre>

DSBulk supports the following three commands:

| Command  | Description |
|----------|-------------|
| `load`   | Load data from external files into Apache Cassandra™   |
| `unload` | Unload data from Apache Cassandra™ into files | 
| `count`  | Compute statistics about a Cassandra table, such as the total number of rows and other metrics |

DSBulk has dozens of options. Here are some of the most common ones:

| Option        | Description |
|---------------|-------------|
| `url`         | URL or path of the resource(s) to read from or write to |
| `k`           | Keyspace used for loading/unloading/counting    |
| `t`           | Table used for loading/unloading/counting  | 
| `m`           | Mapping from file fields to table columns  |
| `cl`          | Consistency level to use for reading or writing (`LOCAL_ONE` is the default) |
| `header`      | Enable or disable whether the files to read or write begin with a header line |
| `logDir`      | Directory for logs (current directory is the default) |
| `query`       | CQL statement to use for loading/unloading/counting |
| `skipRecords` | Number of non-header lines to skip when reading a file |

You can learn more about these and other options from the help page:
```
dsbulk help
```

[continue](command:katapod.loadPage?step3){.orange_bar}