---
title: Competition
draft: false
tags:
  - winelore
---
[[Competition]] is an **Entity** that represents, of course, a [[Wine]] [[Competition]].

> [!info]
> Please note that [[Competition]] data structure doesn't hold information about [[WineSample]]s, [[WineSampleAssessment]]s or [[CommissionParticipant]]s. This information is related rather to [[Commission]]s than to [[Competition]]s.

## Structure
- `id` -- **Id** of the [[Competition]], an unchangeable [UUIDv4](https://en.wikipedia.org/wiki/Universally_unique_identifier).
- `organizer` -- **Organizer** (creator) (its [[AUID]]) of the [[Competition]], an unchangeable `64-bit` `integer`.
- `name` -- [[Competition.Name]] of the [[Competition]], an unchangeable `string`. Once the [[Competition]] is created, its name cannot be changed.
- `plannedStartAt` -- When the [[Competition]] is supposed **to start**, a changeable [[Timestamp]].

> [!example] 
> - `id` = `"5f2afa21-7668-4db3-b949-159c8a7ab31b"`
> - `organizer` = `10`
> - `name` = `"La Competition"`
> - `plannedStartAt` = `1387321861`