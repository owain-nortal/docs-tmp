# metadata  

the metadata subcommand enables exploring and updating the metadata around a data product  

```bash
Usage: neosctl metadata [OPTIONS] COMMAND [ARGS]...

  Manage and browse metadata.

Options:
  --help  Show this message and exit.

Commands:
  browse    Browse external data source metadata.
  pipeline  Manage data source pipelines.
  product   Manage product metadata.
  tag       Manage tags.
```

## flags

| Name | Shorthand | Default | Usage                 |
| ---- | --------- | ------- | --------------------- |
| help |           |         | Get command line help |

---

## browse  

Browse external data source metadata.

```bash
Usage: neosctl metadata browse [OPTIONS] COMMAND [ARGS]...

  Browse external data source metadata.

Options:
  --help  Show this message and exit.

Commands:
  databases         List databases by source type.
  dataset-metadata  Get dataset metadata by source type, database and...
  datasets          List datasets by source type and database.
  source-types      List source types.
```

### flags

| Name | Shorthand | Default | Usage                 |
| ---- | --------- | ------- | --------------------- |
| help |           |         | Get command line help |

---

### databases  

List databases by source type. The available source types are 

- mysql  
- mongodb  
- postgres  

```bash
Usage: neosctl metadata browse databases [OPTIONS]

  List databases by source type.

Options:
  -s, --source-type TEXT  [required]
  --help   Show this message and exit.
```

### flags

| Name        | Shorthand | Default | Usage                                                |
| ----------- | --------- | ------- | ---------------------------------------------------- |
| help        |           |         | Get command line help                                |
| source-type | s         |         | Required flag to define the source type the database |

---

### dataset-metadata  

Get dataset metadata by source type, database and dataset urn <todo> Need more here on this

```bash
Usage: neosctl metadata browse dataset-metadata [OPTIONS]

  Get dataset metadata by source type, database and dataset urn.

Options:
  -s, --source-type TEXT   [required]
  -d, --database TEXT [required]
  -du, --dataset-urn TEXT  [required]
  --helpShow this message and exit.
```

### flags

| Name        | Shorthand | Default | Usage                                                |
| ----------- | --------- | ------- | ---------------------------------------------------- |
| help        |           |         | Get command line help                                |
| source-type | s         |         | Required flag to define the source type the database |
| database    | d         |         | Required flag to define the database                 |
| dataset-urn | du        |         | Required flag to define the dataset-urn              |

---

### datasets

List datasets by source type and database.

```bash
Usage: neosctl metadata browse datasets [OPTIONS]

  List datasets by source type and database.

Options:
  -s, --source-type TEXT  [required]
  -d, --database TEXT[required]
  --help   Show this message and exit.
```

### flags

| Name        | Shorthand | Default | Usage                                                |
| ----------- | --------- | ------- | ---------------------------------------------------- |
| help        |           |         | Get command line help                                |
| source-type | s         |         | Required flag to define the source type the database |
| database    | d         |         | Required flag to define the database                 |

---

### source-types

List source types. <todo> need more here  

```bash
Usage: neosctl metadata browse source-types [OPTIONS]

  List source types.

Options:
  --help  Show this message and exit.
```

### flags

| Name | Shorthand | Default | Usage                 |
| ---- | --------- | ------- | --------------------- |
| help |           |         | Get command line help |

---

```bash
neosctl --profile <name> metadata browse source-types 
```

## pipeline

Manage data source pipelines. <todo> need more here 

### add

  Add an ingestion pipeline.

```bash
Usage: neosctl metadata pipeline add [OPTIONS]

  Add an ingestion pipeline.

Options:
  -n, --name TEXT [required]
  -s, --schedule TEXT  Pipeline schedule in crontab format (e.g. "* * * * *")  [required]
  -st, --schedule-timezone TEXT  [required]
  -sr, --source TEXT   Data source DSN (e.g.mysql://user:pass@host:3306/dbname) [required]
  -it, --include-tables Applies only to relational DBs  [default: True]
  -iv, --include-views Applies only to relational DBs  [default: True]
  --help Show this message and exit.
```

crontab help can be found [here](./cli-crontab.md#crontab)  

### flags

| Name              | Shorthand | Default | Usage                                                    |
| ----------------- | --------- | ------- | -------------------------------------------------------- |
| help              |           |         | Get command line help                                    |
| name              | n         |         | name of the pipeline                                     |
| schedule          | s         |         | set the pipeline schedual in crontab format              |
| schedule-timezone | st        |         | Timezone for the schedule                                |
| source            | sr        |         | Data source DSN (e.g.mysql://user:pass@host:3306/dbname) |
| include-tables    | it        | true    | Applies only to relational DBs                           |
| include-views     | iv        | true    | Applies only to relational DBs                           |

### remove

Remove an ingestion pipeline.

Usage: neosctl metadata pipeline remove [OPTIONS]

Remove an ingestion pipeline.

Options:
  -n, --name TEXT  [required]
  --help Show this message and exit.




## product

Manage product metadata.  

### description

  Add a product description.
### field-description

  Add a product field description.

### field-tag

  Add a product field tag.

### get

  Get data product metadata.

### quality-expectations

  Get data product quality expectations.

### quality-profiling

  Get data product quality profiling.

### quality-validations

  Get data product quality validations.

### remove-field-tag

  Remove a product field tag.

### remove-tag

  Remove a product tag.

### tag

  Add a product tag.

## tag

Manage tags.

### add
  
Add a tag.

### list

  List tags.

### remove

  Remove a tag.
