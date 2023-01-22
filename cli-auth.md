# auth  

The auth subcommand is used to login to neos using a profile. It uses the IAM api to facilitate authenticating and obtaining a time limited authentication token. The authentication token lasts for <TODO> 10 minutes before it will require refreshing  

(we should add refresh as an option on the CLI)

## login

The login subcommand authenticates and populates the profiles access token for the referenced profile user, if no password flag is supplied, then there will be a prompt for a password  

```bash
neosctl --profile <name> auth login  
```

The --password flag enables passing in a password from the commandline without prompting.  

## logout  

The logout subcommand removes the access token and the refresh token for the defined profile.  

```bash
neosctl --profile <name> auth logout  
```
