---
title: Credentials
draft: false
tags:
  - axusid
---
[[Credentials]] is an **Entity** and hold the most important information for every user -- [[AUID]]/[[Password]] Hash pair and the user's [[Username]].
## Structure
- `auid` -- [[AUID]] of the user, an unchangeable `64-bit` `integer`.
- `username` -- [[Username]] of the user, a changeable `string`.
- `passwordHash` -- hash of the user's [[Password]], a changeable `string`. Is always set to `NULL` in responses due to security reasons.
- `createdAt` -- time when the [[Credentials]] was created (in fact when the account was created), an unchangeable [[Timestamp]].

> [!example] 
> [[Credentials]] of [[likespro]]:
> - `auid` = `1`
> - `username` = `"likespro"`
> - `passwordHash` = `NULL`
> - `createdAt` = `1387321861`
## Common Credentials
| [[AUID]] | [[Username]] | Description                                                                                                                                      |
| -------- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `0`      | `@everyone`  | A special user. See [everyone-user](everyone-user "mention") for more information.                                                               |
| `1`      | `@likespro`  | **likespro** in person. Creator of the [[AXUS™]] system.                                                                                         |
| `2`      | `@axusid`    | [[AXUS™ ID]] account. All permissions regarding [[AXUS™ ID]] should be specified in the context of this account.                                 |
| `3`      | `@axus`      | [[AXUS™]] account.                                                                                                                               |
| `4`      | `@shadow`    | **shadow**'s account.                                                                                                                            |
## Related Key Terms
#### [[AUID]]