---
title: Wine.Name
draft: false
tags:
  - winelore
---
[[Wine.Name]] is a **Value** data structure that holds the name of a [[Wine]].

You can see its constraints in the [[#`Wine.Name.IsInvalidException`]] section.
## Related Exceptions
Read our [[AXUS™ Default Exception System]] firstly.
#### `Wine.Name.IsInvalidException`
- `Wine.Name.LengthIsInvalidException` -- throws when the passed [[Wine.Name]] value is longer than `64` characters long.
- `Wine.Name.StartsOrEndsWithSpaceException` -- throws when the passed [[Wine.Name]] value starts or ends with a space (`' '` symbol).