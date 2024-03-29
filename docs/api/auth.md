# API Authorisation

Certain endpoints on the Tachi API require permissions.
This page covers how to present your permissions to the server, and what those permissions are.

*****

## Authorising Requests

There are two ways to authorise a request. The first one involves API keys.

To use authentication with a request, you should set a HTTP header of:

```
Authorization: Bearer API_KEY
```

Where API_KEY is the api key you wish to use.

The other way to authorise a request is with your session cookie. This is **NOT** recommended
for normal use, and is instead a way for logged-in users to interact with the API as themselves.

To use authentication in this way, simply make a request with your `ktchi_production_session` or
`btchi_production_session` cookie.

The reason for this second authentication method is so that, when a user logs in, they can use
the cookie they were set to also interact with the API.

## Getting Tokens

Users may create API tokens at Settings > API Tokens. They may also revoke these tokens.

## Permissions

An API key does not implicitly have permission to do anything on a users behalf for security reasons.
Some endpoints require specific permissions, such as a `score:submit` permission for submitting scores.

!!! warning
	API keys **can not** have their permissions altered once set, a new key must be generated.

!!! info
	Cookie-based authentication always has *all* permissions for the user.

### Table Of Permissions

The table of permissions is as follows.

| Permission | Description |
| :: | :: |
| `score:submit` | Perform requests that could submit scores for the user. |