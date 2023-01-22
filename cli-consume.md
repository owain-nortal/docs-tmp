# consume  

The consume subcommand is used to enable quick and easy commandline access to consumption of published data products using a query in trino format SQL. Trino sytax documentation is available [here](https://trino.io/docs/current/sql.html)

## query

The query subcommand enables sending a trino sql like query to get the contents of a data product  

```bash
neosctl --profile <name> consume query 'sql statement'  
```

### query example

This is an example of consuming 10 rows of data in the data product called 'worker' which is in the postgres engine.  

```bash  
neosctl --profile some-user consume query 'select * from postgres.neos.worker limit 10'
```
