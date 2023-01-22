# IAM

The iam subcommand enables interacting with the neos IAM API.  

## create  

The create subcomand is used to upload a new user IAM policy json file. Once created , it is necessary to use the update sub command to make any changes to an existing IAM policy.  

```bash
neosctl --profile <name> iam create <file path> 
```

## delete

The delete subcommand is used to delete a users IAM policy using the neos users NRN (Neos Resource Name), the URN is a required argument

```bash
neosctl --profile <name> iam delete <urn>
```

## get

The get sub command is used to get a users IAM policy using the neos users NRN (Neos Resource Name), the URN is a required argument.  

```bash
neosctl --profile <name> iam get <urn>
```

## list

The list sub command is used to list all the IAM policies available to the user executing the command. Using the --page flag it is possbile to specify a specific page of the result set, Using the --page-size flag, the number of results per page can be configured. The --resource flag enables defining a specific resourc NRN (Neos Resource Name)

```bash
neosctl --profile <name> iam list 
```

## update  

<TODO> IS this spelling of principle vs principal  

The update sub command is used to update an IAM profile with a new IAM policy, it is require to speficy both the principle and the path to the updates IAM policy document.  

```bash  
neosctl --profile <name> iam update <principle> <filepath> 
```
