# Ricoh Auth Client for Python

Auth Python Library for Ricoh API.

## Requirements

You need

- Ricoh API Client Credentials (client_id & client_secret)
- Ricoh ID (user_id & password)

If you don't have them, please register yourself and your client from [THETA Developers Website](http://contest.theta360.com/).

## Install

```sh
$ pip install --upgrade git+https://github.com/ricohapi/auth-py.git
```

## Authentication

```Python
from ricohapi.auth.client import AuthClient

client = AuthClient(client_id, client_secret)
client.set_resource_owner_creds(user_id, user_pass)
client.session(AuthClient.SCOPES['MStorage'])
print(client.get_access_token())
```

## SDK API

### Constructor

```Python
client = AuthClient('<your_client_id>', '<your_client_secret>')
```

### Set resource owner credentials

This service only supports the resource owner password credentials flow.

```Python
client.set_resource_owner_creds('<your_user_id>', '<your_password>')
```

### Open session

```Python
client.session('<scope>')
```

### Obtain the valid access token

The access token will be refreshed automatically as needed.

```Python
client.get_access_token()
```
