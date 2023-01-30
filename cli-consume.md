# consume  

The consume subcommand is used to enable quick and easy command line access to consumption of published data products using a query in trino format SQL. Trino sytax documentation is available [here](https://trino.io/docs/current/sql.html)

```bash
Usage: neosctl consume [OPTIONS] COMMAND [ARGS]...

  Consume published data products.

Options:
  --help  Show this message and exit.

Commands:
  query  Query a published data product.
```

### flags

|Name|Shorthand|Default|Usage|
|----|---------|-------|-----|
|help|||Get command line help|

---

## query

The query subcommand enables sending a trino sql like query to get the contents of a data product  

```bash
Usage: neosctl consume query [OPTIONS] STATEMENT

  Query a published data product.

Arguments:
  STATEMENT  [required]

Options:
  --help  Show this message and exit. 
```

### flags  

|Name|Shorthand|Default|Usage|
|----|---------|-------|-----|
|help|||Get command line help|

### query example

This is an example of consuming 10 rows of data in the data product called 'worker' which is in the postgres engine.  

```bash  
neosctl --profile some-user consume query 'select * from postgres.neos.worker limit 10'
```

---
