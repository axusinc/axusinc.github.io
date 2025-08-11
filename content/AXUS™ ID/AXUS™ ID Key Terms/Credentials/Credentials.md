---
title: Credentials
draft: false
tags:
  - axusid
---
[[Credentials]] is an Entity and hold the most important information for every user -- [[AUID]]/[[Password]] Hash pair and the user's [[Username]].

> [!example]
> [[likespro]] can have the following [[Credentials]]:
> - [[AUID]] **1**
> - [[Username]] **likespro**
> - [[Password]] Hash **always `NULL`**
## Structure
- `auid` -- [[AUID]] of the user, an unchangeable `64-bit` `integer`.
- `username` -- [[Username]] of the user, a changeable `string`.
- `passwordHash` -- hash of the user's [[Password]], a changeable `string`. Is always set to `NULL` in responses due to security reasons.
- `createdAt` -- time when the [[Credentials]] was created (in fact when the account was created), an unchangeable [[Timestamp]].
## Common Credentials
| [[AUID]] | [[Username]] | Description                                                                                                                                      |
| -------- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `-1`     |              | Not a [[Credentials]] but just a special, utility [[AUID]]. No accounts have this [[AUID]], but it is used in filters and means [[Anyone AUID]]. |
| `0`      | `@everyone`  | A special user. See [everyone-user](everyone-user "mention") for more information.                                                               |
| `1`      | `@likespro`  | **likespro** in person. Creator of the [[AXUS™]] system.                                                                                         |
| `2`      | `@axusid`    | [[AXUS™ ID]] account. All permissions regarding [[AXUS™ ID]] should be specified in the context of this account.                                 |
| `3`      | `@axus`      | [[AXUS™]] account.                                                                                                                               |
| `4`      | `@shadow`    | **shadow**'s account.                                                                                                                            |
