# registy

## get-product

  Get data product details.

Arguments:
  URN  [required]

## list-cores

  List existing registered cores.

## register-core

  Register a core.

  Register a core to recieve an identifier and access key for use in
  deployment.

Arguments:
  PARTITION  Core partition  [required]
  NAME       Core name  [required]

Options:
  --help  Show this message and exit.

## remove-core

  Remove a registered core.

Usage: neosctl registry remove-core [OPTIONS] URN

  Remove a registered core.

Arguments:
  URN  Core urn  [required]

## search

Search published data products across cores.

Arguments:
  SEARCH_TERM  [required]
