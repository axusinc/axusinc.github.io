---
title: AXUS™ ID Quickstart
draft: false
tags:
  - axusid
---
The first thing you have to know — each user has unique **[[AUID]]** (**A**XUS™ **U**ser **ID**entifier), which is an integer and is unchangeable. Click on [[AUID]] to read more info.

If you have [[AUID]] of the user, you can easily derive all his public information. So it is the most important thing that you must know if you are dealing with a user. But don't worry — [[AXUS™ ID]] embeds [[AUID]] in all authorization flows.

> [!warning]
> You can't derive [[AUID]] from [[Token]]s/[[Refresh token]]s, so you need to store [[AUID]] of a user as well as his [[Token]]/[[Refresh token]].

## Authorize User via OAuth2 Implicit Flow

#### Initiate authorization process

To authorize user and get token with some scope, first of all, redirect user to the next **URI**:

```http
https://v0-axus-id-sign-in.vercel.app/oauth/authorize?
response_type=token&
client_id=<APP_AUID>&
redirect_uri=<REDIRECT_URI>&
scope=<FULL_PERMISSION_PATTERN>&
state=<RANDOM_STRING>
```

Here:

* `<APP_AUID>` — **[[AUID]]** of your application account in [[AXUS™ ID]]. For example, [[MasterPay™]] has [[AXUS™ ID]] account with [[AUID]] = `6`. So if you are developing [[MasterPay™]] and now authorize it's user via [[AXUS™ ID]], you must use `6` as `<APP_AUID>`.
* `<REDIRECT_URI>` — URI that [[AXUS™ ID]] will redirect to after authorization process finished (successfully or with errors). For example, if your callback worker listens to [https://example.com/callback](https://example.com/callback) — you should specify `https://example.com/callback` as the `REDIRECT_URI`. [[AXUS™ ID]] will add all the info to the end of the URI as fragment (URI part after `#` symbol).
* `<FULL_PERMISSION_PATTERN>` — [[Full Permission Pattern]] which the token you are creating will have. You can specify multiple [[Full Permission Pattern]]s by separating them with `+` symbol. You can specify `-1` in `from` and `to` fields and [[AXUS™ ID]] will automatically replace them with the user's [[AUID]].
  You can also just leave the `scope` field empty (e. g. if you don't need token to have any scope **or** you don't use [[AXUS™ ID]] permission system in your app).
* `<RANDOM_STRING>` — just a random string. It doesn't matter in **OAuth2 Implicit Flow**.

> [!example] Example of a request
> ```http
> https://v0-axus-id-sign-in.vercel.app/oauth/authorize?
> response_type=token&
> client_id=6&
> redirect_uri=https://example.com/callback&
> scope=-1:-1:6:.*&
> state=AWdhakBWdhkBAsjdW
> ```
> This request will result in [[Token]]/[[Refresh token]] pair with all permissions of the user in context of the user with [[AUID]] `6` (**MasterPay**).

#### Process authorization result

After successful (or not) authorization, [[AXUS™ ID]] redirects user to the following URI:

```http
<REDIRECT_URI>#
access_token=<TOKEN>&
token_type=bearer&
expires_in=<TOKEN_LIFETIME>&
auid=<USER_AUID>&
refresh_token=<REFRESH_TOKEN>&
refreshExpiresIn=<REFRESH_TOKEN_LIFETIME>&
state=<STATE_FIELD_FROM_REQUEST>
```

Here:

* `<REDIRECT_URI>` — the `redirect_uri` field from the request.
* `<TOKEN>` — the [[Token]] with all the requested permissions.
* `<TOKEN_LIFETIME>` — lifetime of [[Token]]/time to expire. Usually, it is `12 hours` when the [[Token]] was issued. When the [[Token]] expires, it will not be valuable anymore and needs to be replaced with a new one. You can create a new **token** with the corresponding [[Refresh token]].
* `<USER_AUID>` — [[AUID]] of the authorized user.
* `<REFRESH_TOKEN>` — the [[Refresh token]], which gives you an ability to replace the [[Token]] with a new one with equal permissions and renewed lifetime.
* `<REFRESH_TOKEN_LIFETIME>` — lifetime of [[Refresh token]]/time to expire. Usually, it is `365 days` when the [[Refresh token]] was issued. When the [[Refresh token]] expires, it will not be valuable anymore and you need to authorize user again.
* `<STATE_FIELD_FROM_REQUEST>` — just the `state` field value in the request.

> [!example] Example of successful response
> ```http
> https://example.com/callback#
> access_token=DznOSMJtzTbOCcad6RoTO467845TrepfPBXQf9WINuJKELwW2-elMg5cn1DpIq96&
> token_type=bearer&
> expires_in=43200&
> auid=1&
> refresh_token=keUqX5pTpf_2Ri08s6PUdVnqY_uzPR_U0o9QG00k-1g2bfjvu0hH9vcHGz1CE_0NEDP4T-B94s3bFiWDd8QsXA0zpB8xD3elXR9SjWedchj02L5EEomN51n1ZwrT2LHc&
> refreshExpiresIn=14515200&
> state=AWdhakBWdhkBAsjdW
> ```

> [!hint]
> Please note that there are some additional fields that [[AXUS™ ID]] adds to the default response format in **OAuth2 Implicit Flow** specification.

> [!warning]
> Currently you can't specify custom [[Token]]s/[[Refresh token]]s lifetime.

## What's next?
Go to [[AXUS™ ID Key Terms]] to learn more about [[AXUS™ ID]] system.
Go to [[AXUS™ ID REST API]] to get more information about dealing with [[AXUS™ ID]] via **REST API**.