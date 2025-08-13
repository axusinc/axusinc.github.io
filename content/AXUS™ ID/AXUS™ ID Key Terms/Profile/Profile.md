---
title: Profile
draft: false
tags:
  - axusid
---
[[Profile]] is an **Entity** that holds public information about user that must be the same accross all [[Variation]]s.
## Structure
- `auid` -- [[AUID]] of the user, an unchangeable `64-bit` `integer`.
- `avatar` -- **Avatar** (it's [[Image.Id]] in [[HyperCDN™]]) of the user, a changeable `nullable` `string`. Currently not supported and therefore is always set to `NULL`.
- `icon` -- **Icon** (it's [[Image.Id]] in [[HyperCDN™]]) of the user, a changeable `nullable` `string`. Currently not supported and therefore is always set to `NULL`. **Icon** is the **logo** of the user on transparent background and is used, for example, when the user's [[AUID]] is **clientId** in [[OAuth 2.0 Authorization]]. So general users don't need this feature.
- `verifiedUsername` -- [[Username]] of the user at the moment of it's [[AXUS™ ID Verification]] **or** `NULL` if the user is **not verified**, a changeable `nullable` `string`. If current actual [[Username]] of the user is not the same as `verifiedUsername`, the user is considered as not verified.
- `createdAt` -- time when the [[Profile]] was created, an unchangeable [[Timestamp]]. Usually [[Profile]] creates on the first request to change something in the user's [[Profile]], so it is **lazy generated**.