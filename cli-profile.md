# profile

## init

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

### init of a sandbox core

If using a NEOS sandbox it is possible to initialise the all the API's to that single sandbox using the '--non-interactive' switch which will use a set of defaults based on the value passed in by the '--host' flag

### Example creating a sandbox profile  

```bash
neosctl --profile test profile init --host somecore.neosdata.net --non-interactive 
```

## delete  

To delete a profile using the delete subcommand  

```bash
neosctl --profile <name> profile delete 
```

## list  

list all the available profiles.  

```bash
neosctl profile list 
```

## view  

To view the contents of a named profile  

```bash
neosctl --profile <name> profile view  
```

## Profile file details  

The default location of the profile file is in the users default home directory with a filename of .neosctl  

each named profile is a json object similar to below.  

```json
{
  "access_token": "",
  "gateway_api_url": "https://some-core.neosdata.net/api/gateway",
  "iam_api_url": "https://iam.neosdata.net/api/iam",
  "ignore_tls": "False",
  "refresh_token": "",
  "registry_api_url": "https://registry.neosdata.net/api/registry",
  "storage_api_url": "https://some-core.neosdata.net/api/storage",
  "user": "some-user"
}
```
| name             | description                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| access_token     | The JWT used to authenticate with the API's this is populated when successfully logged into NEOS |
| gateway_api_url  | The URI of the gateway API                                                                       |
| iam_api_url      | The URI of the IAM API                                                                           |
| ignore_tls       | Defines if TLS should be ignored                                                                 |
| refresh_token"   | ""                                                                                               | The refresh token for refreshing against the IAM service with a new access token |
| registry_api_url | The URI of the registry API                                                                      |
| storage_api_url  | The URI of the storage API                                                                       |
| user"            | The username of the user of the                                                                  |
