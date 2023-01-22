# metadata  

## browse  

Browse external data source metadata.

: databases  

  List databases by source type.

neosctl --profile op metadata browse databases --help
Usage: neosctl metadata browse databases [OPTIONS]

  List databases by source type.

Options:
  -s, --source-type TEXT  [required]
  --help   Show this message and exit.

### dataset-metadata  

Get dataset metadata by source type, database and...

Usage: neosctl metadata browse dataset-metadata [OPTIONS]

  Get dataset metadata by source type, database and dataset urn.

Options:
  -s, --source-type TEXT   [required]
  -d, --database TEXT [required]
  -du, --dataset-urn TEXT  [required]
  --helpShow this message and exit.

### datasets

  List datasets by source type and database.

Usage: neosctl metadata browse datasets [OPTIONS]

  List datasets by source type and database.

Options:
  -s, --source-type TEXT  [required]
  -d, --database TEXT[required]
  --help   Show this message and exit.

### source-types

  List source types.

Usage: neosctl metadata browse source-types [OPTIONS]

  List source types.

Options:
  --help  Show this message and exit.

```bash
neosctl --profile <name> metadata browse source-types 
```

## pipeline

    Manage data source pipelines.

### add

  Add an ingestion pipeline.

Usage: neosctl metadata pipeline add [OPTIONS]

  Add an ingestion pipeline.

Options:
  -n, --name TEXT [required]
  -s, --schedule TEXT  Pipeline schedule in crontab format (e.g. "* * * * *")  [required]

  -st, --schedule-timezone TEXT  [required]
  -sr, --source TEXT   Data source DSN (e.g.mysql://user:pass@host:3306/dbname) [required]

  -it, --include-tablesApplies only to relational DBs  [default: True]

  -iv, --include-views Applies only to relational DBs  [default: True]

  --help Show this message and exit.

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
