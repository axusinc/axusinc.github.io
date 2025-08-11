---
title: User Information
draft: false
tags:
  - axusid
---
[[User Information]] is an aggregation data structure containing user's [[Credentials]], [[Profile]] and some [[Variation]]. It was created for more convenience and performance optimization. Many times applications need to get nearly all public user information at once, hence the [[User Information]] structure was introduced to reduce requests amount.
## Structure
#### Default
- `credentials` -- [[Credentials]] of the user, an unchangeable [[Credentials]] data structure.
- `profile` -- [[Profile]] of the user, an unchangeable [[Profile]] data structure.
- `variation` -- Some [[Variation]] of the user (default [[Variation]] by default), an unchangeable [[Variation]] data structure.
#### In [[AXUS™ ID REST API]]
To make use of [[User Information]] data structure in [[AXUS™ ID REST API]] easier, the structure was simplified (all fields from complex substructures (e. g. [[Credentials]]) were merged):
- `auid` -- [[AUID]] of the user, an unchangeable `64-bit` `integer`.
- `username` -- [[Username]] of the user, a changeable `string`.
- `passwordHash` -- hash of the user's [[Password]], a changeable `string`. Is always set to `NULL` in responses due to security reasons.
- `credentialsCreatedAt` -- time when the credentials where created (in fact when the account was  created), an unchangeable [[Timestamp]].
- `avatar` -- **Avatar** (it's [[Image.Id]] in [[HyperCDN™]]) of the user, a changeable `nullable` `string`. Currently not supported and therefore is always set to `NULL`.
- `icon` -- **Icon** (it's [[Image.Id]] in [[HyperCDN™]]) of the user, a changeable `nullable` `string`. Currently not supported and therefore is always set to `NULL`. **Icon** is the **logo** of the user on transparent background and is used, for example, when the user's [[AUID]] is **clientId** in [[OAuth 2.0 Authorization]]. So general users don't need this feature.
- `verifiedUsername` -- [[Username]] of the user at the moment of it's [[AXUS™ ID Verification]] **or** `NULL` if the user is **not verified**, a changeable `nullable` `string`. If current actual [[Username]] of the user is not the same as `verifiedUsername`, the user is considered as not verified.
- `profileCreatedAt` -- time when the [[Profile]] was created, an unchangeable [[Timestamp]]. Usually [[Profile]] creates on the first request to change something in the user's [[Profile]], so it is **lazy generated**.
- 
#TODO