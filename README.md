# List of Freemail Providers

This repository provides a list of common email providers in csv format.

## JSON file
Check [provider-domains.json](provider-domains.json).

This list is useful when you want check if your user's email address is a
company mail address or not.

Please create a pull request to update the list.


## Rest API

This repository also provide free Rest API endpoint. The api endpoints serves up-to-dated data in the master branch.

When your pull request is merged, https://freemail-providers.s1mplexx.eu will be automatically build and deploy the new version.


#### List all email providers

Request (GET)
```
https://freemail-providers.s1mplexx.eu/api/all
```

Response (200, Content-Type: application/json)
```
[
    ...
    "gmail.com",
    "yahoo.com",
    ...
]
```

#### Query provider by email address or domain

Request
```
https://freemail-providers.s1mplexx.eu/api/<email or domain>
```

Response

 - 200 - when email or domain is in the provider list
 - 404 - when email or domain is not in the provider list


Example request

```
https://freemail-providers.s1mplexx.eu/api/foo@gmail.com
https://freemail-providers.s1mplexx.eu/api/gmail.com
https://freemail-providers.s1mplexx.eu/api/bar.com
```
