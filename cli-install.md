# Installation of neosctl  

At present neosctl is written as a python and can be installed on an existing operating system where python and pip are installed simply using  

```bash
pip install --update neosctl 
```

To get the operating system ready to run neosctl please go to the following sections  

Install on [Windows](#install-on-windows)  

Install on [Mac](#install-on-mac)  

Install on [Linux](#install-on-linux)  

## Getting help  

There is a "--help" switch that will return help for neosctl and any of the sub commands available in neosctl  

```bash
neosctl --help  
```

## Setting up neosctl profile  

In order to interact with NEOS it is necessary to configure at least one neosctl profile. It is possible to have any many profiles which can be used to connect to one or more NEOS cores and the IAM and registry either as one user or as many different users. A single profile and only connect to a single neos core at this time.  

The profie is stored as a file in the default home directory of the CLI user. the file is called '.neosctl'  

In order to initialise a profile the 'profile' subcommand is used.  

```bash
neosctl profile  
```

A profile name can be any alpha numeric string. Almost all neosctl commands will require specifying which profile is in use using the '--profile' flag  

It is possible to specify the API endpoints for neosctl as a part of the neosctl command instead of using a profile should this be necessary.  

To specify the gateway api endpoint  

```bash
--gateway-api-url
```

To specify the registry API endpoint  

```bash
--registry-api-url 
```

To specify the IAM registry API endpoint  

```bash
--iam-api-url
```

To specify the storage API endpoint  

```bash
--storage-api-url
```

## code completion  

It is possible to install code completion for a shell  

The shells that are suported are:  

- bash  
- zsh  
- fish
- powershell
- pwsh

```bash
--install-completion [bash|zsh|fish|powershell|pwsh]
```

To display the code completion code as a base for customisation  

--show-completion [bash|zsh|fish|powershell|pwsh]

## Install on Windows  

Install neosctl on Windows  

## Install on Mac  

Install neosctl on Mac  

## Install on Linux  

Install neosctl on Linux  

