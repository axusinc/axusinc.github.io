---
title: AXUS™ Default Exception System
draft: false
tags:
---
[[AXUS™ Default Exception System]] was created to standartize **Exception**s accross multiple products. So let's take a look on its [[#Guidelines]].
## Guidelines
- Each **Exception** has its own unique name -- `className`. It literlly represents the corresponding classes names in SDKs. Always when some **Exception** is metioned, its `className` is used.
- Each datastructure can have `2` general **Exception**s: **IsInvalidException** and **IsIncorrectException**.
- **IsInvalidException** is a parental **Exception** for all **Exception**s that throws when creating a data structure that **can't** even exist with the passed parameters. For example, they can be thrown if you pass too long `string` to [[First Name]].
- **IsIncorrectException** is a parental **Exception** for all **Exception**s that throws when a runtime **Exception** regarding a data structure occured. For example, they can be thrown if you try to access a [[Variation]] for which you have no access.
- Either **IsInvalidException** or **IsIncorrectException** can't be thrown themselves, they are just parental classes for other **Exception**s.