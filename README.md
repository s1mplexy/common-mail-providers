# List of Freemail Providers

This repository provides a list of common email providers in json format.

Requirements to be on this list:
- The domain is used by several people to receive and send e-mails
- Anyone can register for the domain either for free or paid
- It is **not** a throwaway email domain

## TXT file
Txt list. This file is intended for pull requests. Please look below for the json file.

Check [providers.txt](providers.txt).
Please create a pull request to update the list.

## JSON file
Check [provider-domains.json](provider-domains.json).

This list is useful if you want to check whether your user's email address is a personal email address or not.
Companies usually use their own domain for their employees' communication.

Please create a pull request for "providers.txt", this list will then automatically be updated.


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
{
  "domains": [
    ...
    "gmail.com",
    "yahoo.com",
    ...
  ]
}
```

#### Query provider by email address or domain

Request
```
https://freemail-providers.s1mplexx.eu/api/<email or domain>
```

Response

 - 200 - when email or domain is in the provider list
 ``` {"domains":"gmail.com","status":"found"} ```
 - 404 - when email or domain is not in the provider list
 ```{"domains":"google.com","status":"notinlist"}```
 ```{"domains":"","status":"error-empty-request"}```


Example request

```
https://freemail-providers.s1mplexx.eu/api/foo@gmail.com
https://freemail-providers.s1mplexx.eu/api/gmail.com
https://freemail-providers.s1mplexx.eu/api/bar.com
```
