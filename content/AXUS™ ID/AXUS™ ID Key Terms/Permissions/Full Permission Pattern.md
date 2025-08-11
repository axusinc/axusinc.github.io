---
title: Full Permission Pattern
draft: false
tags:
  - axusid
---
[[Full Permission Pattern]] is used to grant multiple similar permissions at once. It's structure is similar to [[Full Permission]] but [[Permission Pattern]] is used instead of [[Permission]].
## Structure
#### Default
- `from` -- [[AUID]] of the issuer of the permissions, an unchangeable `64-bit` `integer`.
- `to` -- [[AUID]] of the grantee of the permissions, an unchangeable `64-bit` `integer`.
- `context` -- [[AUID]] of the context (see [[Full Permission#Context]]) in with all the permissions are granted, an unchangeable `64-bit` `integer`.
- `permissionPattern` -- [[Permission Pattern]] itself, a [RegEx](https://en.wikipedia.org/wiki/Regular_expression) `string`.
#### In [[AXUS™ ID REST API]]
When dealing with [[AXUS™ ID REST API]], [[Full Permission Pattern]] is just a string and must be specified in the next format: `<FROM>:<TO>:<CONTEXT>:<PERMISSION_PATTERN>`. Here:
* `<FROM>` — `from` field.
* `<TO>` — `to` field.
* `<CONTEXT>` — `context` field.
* `<PERMISSION_PATTERN>` — `permissionPattern` field.