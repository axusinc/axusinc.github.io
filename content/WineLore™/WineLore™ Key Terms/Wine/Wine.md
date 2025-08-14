---
title: Wine
draft: false
tags:
  - winelore
---
[[Wine]] is an entity that represents, of course, a [[Wine]].
## Structure
- `id` -- **Id** of the [[Wine]], an unchangeable [UUIDv4](https://en.wikipedia.org/wiki/Universally_unique_identifier).
- `producer` -- **Producer** (creator) (its [[AUID]]) of the [[Wine]], an unchangeable `64-bit` `integer`.
- `name` -- [[Wine.Name]] of the [[Wine]], an unchangeable `string`. Once the [[Wine]] is created, its name cannot be changed.
- `iteration` -- **Iteration** of the [[Wine]], an unchangeable [[Iteration]].
- `color` -- [[Wine.Color]] of the [[Wine]], an unchangeable [[Wine.Color]].
- `type` -- [[Wine.Type]] of the [[Wine]], an unchangeable [[Wine.Type]].
- `createdAt` -- time when the [[Wine]] was created, an unchangeable [[Timestamp]].

> [!example] 
> - `id` = `"5f2afa21-7668-4db3-b949-159c8a7ab31b"`
> - `producer` = `10`
> - `name` = `"Champagne"`
> - `iteration` = `1`
> - `color` = `WHITE`
> - `type` = `SPARKLING`
> - `createdAt` = `1387321861`

## Related Exceptions
Read our [[Global Exception System]] firstly.
#### `Wine.IsIncorrectException`
- `Wine.ProducerAndNameAndIterationAreAlreadyUsedException` -- throws when [[Wine]] **Producer**, [[Wine.Name]] and [[Iteration]] combination is already used.
## Related Key Terms
#### [[Wine.Name]]
#### [[Wine.Color]]
#### [[Wine.Type]]