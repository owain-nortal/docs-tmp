neosctl 

## Overview of neosctl 

The neosctl commandline tool enables management of every aspect in NEOS. All the API's that are developed in the NEOS ecosystem can be controlled using the neosctl command line application. 

There are 4 main API components to the NEOS ecosystem 

### NEOS Core

NEOS core is the heart of the NEOS operating system, it is used to store and create data products and the data product data. 

### NEOS IAM 

NEOS Identity and Access Management (IAM) is a centralised system for managing authentication and authorisation. 

Authentication is identifying and validating who the user of NEOS  

Authorisation is establishing what API actions a NEOS user can request of the API's 

### NEOS Registry 

NEOS Registry is used as the centralised registry of all the NEOS data products and associated metadata.  

### NEOS Storage 

## Installation of neosctl 

At present neosctl is written as a python and can be installed on an existing operating system where python and pip are installed simply using  

```bash 
pip install --update neosctl 
```

To get the operating system ready to run neosctl please go to the sections 

running on windows <TODO>
running on mac <TODO>
running on linux <TODO>


## Getting help 

There is a "--help" switch that will return help for neosctl and any of the sub commands available in neosctl 

```bash
neosctl --help  
```

## Setting up neosctl  

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

#### code completion 

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

To display the code completion code as a base for customisation the 

--show-completion [bash|zsh|fish|powershell|pwsh]


### init 

In order to create a profile the init subcommand is used 

```bash
neosctl --profile <name> profile init  
```
A repeated call to the init subcommand will update any existing profile with new values. 

Options  

The hostname of the NEOS core can be specified using the --host flag, this should be used in conjuction with the --non-interactive flag when setting up a profile for a NEOS sandbox. e.g. 'some-sandbox.neosdata.io'

```bash
-h , --host "TEXT" 
```

The NEOS core gateway API endpoint can be specified using the --gateway-api-url flag, typically this value will have the neos core hostname follwed by '/api/gateway' e.g. 'https://some-core.neosdata.net/api/gateway'

```bash 
-g, --gateway-api-url TEXT
```
The NEOS registry API endpoint can be specified using the --registry-api-url flag, typically this value will have the centralised registry DNS name [TBC] followed by '/api/registry' e.g' 'https://registry.neosdata.net/api/registry'  

```bash 
  -r, --registry-api-url TEXT
```

The NEOS IAM API endpoint can be specified using the --iam-api-url flag, typically this valye will have the centralised registry DNS name [TBC] folled by '/api/iam' e.g. 'https://iam.neosdata.net/api/iam'  

```bash 
-i, --iam-api-url TEXT
```

The NEOS Storage API endpoint can be specified using the --storage-api-url flag, typically this valye will have the neos core hostname folled by '/api/storage' e.g. 'https://some-core.neosdata.net/api/storage'  

```bash
-s, --storage-api-url TEXT
```

The username of the neos user that will be used for this profile can be specified using the --username flag 

```bash
-u, --username TEXT
```

To ingore API TLS the --ignore-tls flag can be used, this is not recommended outside of development environments 

```bash
--ignore-tls                 
```

To complement setting up a sandbox envrionmebt the --host flag , the --non-interactive flag will populate the api urls for all the API's using the value of --host. 

```bash
--non-interactive            
```

#### init of a sandbox core 

If using a NEOS sandbox it is possible to initialise the all the API's to that single sandbox using the '--non-interactive' switch which will use a set of defaults based on the value passed in by the '--host' flag 

#### Example creating a sandbox profile  

```bash
neosctl --profile test profile init --host somecore.neosdata.net --non-interactive 
```

### delete 

To delete a profile using the delete subcommand 

```bash
neosctl --profile <name> profile delete 
```

### list 

list all the available profiles. 


```bash 
neosctl profile list 
```

### view 

To view the contents of a named profile 

```bash
neosctl --profile <name> profile view  
```

### Profile file details 

The default location of the profile file is in the users default home directory with a filename of .neosctl 

each named profile is a json object similar to below.  

```json
  "access_token": "",
  "gateway_api_url": "https://some-core.neosdata.net/api/gateway",
  "iam_api_url": "https://iam.neosdata.net/api/iam",
  "ignore_tls": "False",
  "refresh_token": "",
  "registry_api_url": "https://registry.neosdata.net/api/registry",
  "storage_api_url": "https://some-core.neosdata.net/api/storage",
  "user": "some-user"
```

"access_token" - contains a JWT used to authenticate with the API's this is populated when successfully logged into NEOS
"gateway_api_url" - contains the URI of the gateway API 
"iam_api_url" - contains the URI of the IAM API 
"ignore_tls": "False" - defines if TLS should be ignored 
"refresh_token": "" - refresh token for refreshing against the IAM service with a new access token 
"registry_api_url" - contains the URI of the registry API 
"storage_api_url" - contains the URI of the storage API 
"user": - contains the username of the user of the 


## auth 

The auth subcommand is used to login to neos using a profile. It uses the IAM api to facilitate authenticating and obtaining a time limited authentication token. The authentication token lasts for <TODO> 10 minutes before it will require refreshing 

(we should add refresh as an option on the CLI)

### login 

The login subcommand authenticates and populates the profiles access token for the referenced profile user, if no password flag is supplied, then there will be a prompt for a password  

```bash
neosctl --profile <name> auth login  
```
The --password flag enables passing in a password from the commandline without prompting. 

### logout 

The logout subcommand removes the access token and the refresh token for the defined profile.   

```bash
neosctl --profile <name> auth logout  
```

## consume 

The consume subcommand is used to enable quick and easy commandline access to consumption of published data products using a query in trino format SQL. <TODO - link to trino , or more on this > 


### query 

The query subcommand enables sending a trino sql like query to get the contents of a data product 

```bash
neosctl --profile <name> consume query 'sql statement'  
```

#### query example

This is an example of consuming 10 rows of data in the data product called 'worker' which is in the postgres engine.  

```bash 
neosctl --profile some-user consume query 'select * from postgres.neos.worker limit 10'
```

<TODO - check the above sql is correct>

## iam 

The iam subcommand enables interacting with the neos IAM API. 

### create 

The create subcomand is used to upload a new user IAM policy json file. 

```bash
neosctl --profile <name> iam create <file path> 
```

### delete  

The delete subcommand is used to delete a user IAM policy using the neos users NRN (Neos Nesource Name), the URN is a required argument

```bash
neosctl --profile <name> iam delete <urn>
```


### get 

### list 

### update 



## metadata 

## product 

## profile 

## registy 

## spark 

## storage 

