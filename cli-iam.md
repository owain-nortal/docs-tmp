# IAM

The iam subcommand enables interacting with the neos IAM API.  

```bash
Usage: neosctl iam [OPTIONS] COMMAND [ARGS]...

  Manage access policies.

Options:
  --help  Show this message and exit.

Commands:
  create  Create an IAM policy.
  delete  Delete an existing IAM policy.
  get     Get an existing IAM policy.
  list    List existing policies.
  update  Update an existing IAM policy.

```

## flags

| Name | Shorthand | Default | Usage                 |
| ---- | --------- | ------- | --------------------- |
| help |           |         | Get command line help |

---

## create  

The create subcomand is used to upload a new user IAM policy json file. Once created , it is necessary to use the update sub command to make any changes to an existing IAM policy.  

```bash
Usage: neosctl iam create [OPTIONS] FILEPATH

  Create an IAM policy.

Arguments:
  FILEPATH  Filepath of the user policy json payload  [required]

Options:
  --help  Show this message and exit.
```

### flags

| Name | Shorthand | Default | Usage                 |
| ---- | --------- | ------- | --------------------- |
| help |           |         | Get command line help |

---

## delete

The delete subcommand is used to delete a users IAM policy using the neos users NRN (Neos Resource Name), the URN is a required argument

```bash
Usage: neosctl iam delete [OPTIONS] USER_NRN

  Delete an existing IAM policy.

Arguments:
  USER_NRN  [required]

Options:
  --help  Show this message and exit.
```

### flags

| Name | Shorthand | Default | Usage                 |
| ---- | --------- | ------- | --------------------- |
| help |           |         | Get command line help |

---

## get

The get sub command is used to get a users IAM policy using the neos users NRN (Neos Resource Name), the URN is a required argument.  

```bash
Usage: neosctl iam get [OPTIONS] USER_NRN

  Get an existing IAM policy.

Arguments:
  USER_NRN  [required]

Options:
  --help  Show this message and exit.
```

### flags

| Name | Shorthand | Default | Usage                 |
| ---- | --------- | ------- | --------------------- |
| help |           |         | Get command line help |

---

## list

The list sub command is used to list all the IAM policies available to the user executing the command

```bash
Usage: neosctl iam list [OPTIONS]

  List existing policies.

Options:
  --page INTEGER       Page number.  [default: 1]
  --page-size INTEGER  Page size number.  [default: 10]
  --resource TEXT      Resource nrn.
  --help               Show this message and exit.
```

### flags

| Name      | Shorthand | Default | Usage                                           |
| --------- | --------- | ------- | ----------------------------------------------- |
| help      |           |         | Get command line help                           |
| page      |           |         | Get a specific page number from the results set |
| page-size |           | 10      | Set the number of items per page                |
| resource  |           |         | Use a specific resource Neos Resource Name      |

---

## update  

The update sub command is used to update an IAM profile with a new IAM policy, it is require to speficy both the principle and the path to the updates IAM policy document. The Principal UUID can be discovered at this time either by running a command you do not have sufficent permissions to execute and will get your UUID in the error message, or looking up in the keycoak user interface as your user.  

```bash  
Usage: neosctl iam update [OPTIONS] PRINCIPAL FILEPATH

  Update an existing IAM policy.

Arguments:
  PRINCIPAL  Principal uuid  [required]
  FILEPATH   Filepath of the user policy json payload  [required]

Options:
  --help  Show this message and exit.
```

### flags

| Name | Shorthand | Default | Usage                 |
| ---- | --------- | ------- | --------------------- |
| help |           |         | Get command line help |

---

