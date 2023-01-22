# spark

## add-job

  Assign a spark job.

  Usage: neosctl spark add-job [OPTIONS] PRODUCT_NAME

  Assign a spark job.

  Assign and configure a spark job for a data product. This will result in a
  one off run of the spark job.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  -f, --job-filepath TEXT  [required]

## csv-job

  Ingest a csv file into a data product.

Usage: neosctl spark csv-job [OPTIONS] PRODUCT_NAME

  Upload a csv file for processing into a data product.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  -d, --delimiter TEXT     csv delimiter  [default: ,]
  -q, --quote-char TEXT    csv quote char
  -w, --write-mode TEXT    csv write mode [overwrite|append]
  -f, --job-filepath TEXT  [required]

## job-history

Get history of spark applications.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  --help  Show this message and exit.

## job-logs

Get logs for a spark job.

  Get logs for a spark job.

  Defaults to current application logs, previous application logs or a
  specific scheduled run can be requested.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  -s, --suffix TEXT
  -r, --run TEXT

## job-status

  Get status of a spark job.

  Defaults to current application status, previous application status or a
  specific scheduled run can be requested.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  -s, --suffix TEXT
  -r, --run TEXT

## remove-job

Remove assigned spark job.

Usage: neosctl spark remove-job [OPTIONS] PRODUCT_NAME

  Remove assigned spark job.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  --force  Force remove even if application is still running.  [default:
           False]

## reschedule-job

Reschedule an assigned spark job.
  Reschedule an assigned spark job.

  Update existing scheduled spark job run schedule.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  -s, --schedule TEXT  Schedule in crontab format (e.g. "* * * * *")
                       [required]

  --force              Force reschedule even if application is still running.
                       [default: False]

## run-history

Get history of spark application runs.

  Get history of spark application runs.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  -s, --suffix TEXT

## schedule-job

Schedule an assigned spark job.

Schedule a spark job once it is configured correctly to run periodically.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  -s, --schedule TEXT  Schedule in crontab format (e.g. "* * * * *")
                       [required]

## secret

Manage secrets for a spark job.

## add

Add a set of secrets for a spark job.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  -s, --secret TEXT  Secret in the form key:value  [required]

## get

Get existing secret keys.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

## remove

Remove secret.

Usage: neosctl spark secret remove [OPTIONS] PRODUCT_NAME

  Remove secret.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

## remove-key

Remove a set of keys from a secret.

Usage: neosctl spark secret remove-key [OPTIONS] PRODUCT_NAME

  Remove a set of keys from a secret.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  -k, --key TEXT  Key name you wish to remove from secret  [required]

## update

Update existing secrets.

 This will overwrite existing keys, and add new keys, any keys that already
  exist but aren't provided will remain.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  -s, --secret TEXT  Secret in the form key:value  [required]

## trigger-job

Trigger assigned spark job.

Trigger an additional run of a spark job.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

## unschedule-job

Unschedule a scheduled spark job.

  Unschedule a scheduled spark job.

  Remove existing scheduled spark job.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  --force  Force unschedule even if application is still running.  [default:
           False]

## update-job

Update an assigned spark job.

 Update the assigned spark job file and/or the spark job configuration
  values.

Arguments:
  PRODUCT_NAME  Data Product name  [required]

Options:
  -f, --job-filepath TEXT
