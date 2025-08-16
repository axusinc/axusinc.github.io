---
title: Commission
draft: false
tags:
  - winelore
---
[[Commission]] is an **Entity** that represents a [[Competition]] [[Commission]].

> [!info]
> Each [[Commission]] **must** be approved by [[WineLore™]] administrators before start.
## Structure
- `id` -- **Id** of the [[Commission]], an unchangeable [UUIDv4](https://en.wikipedia.org/wiki/Universally_unique_identifier).
- `competitionId` -- **Id** of the [[Competition]] related to the [[Commission]], an unchangeable [UUIDv4](https://en.wikipedia.org/wiki/Universally_unique_identifier).
- `name` -- [[Commission.Name]] of the [[Commission]], an unchangeable `string`. Once the [[Competition]] is created, its name cannot be changed.
- `isApproved` -- **Approval** status of the [[Commission]], a changeable `bool`.
- `currentWineSampleId` -- **Id** of the current [[WineSample]] which is assessing by the [[Commission]] at the moment, a changeable `nullable` [UUIDv4](https://en.wikipedia.org/wiki/Universally_unique_identifier).
- `startedAt` -- time when the [[Commission]] work was started, a changeable `nullable` [[Timestamp]].
- `endedAt` -- time when the [[Commission]] work was ended, a changeable `nullable` [[Timestamp]].

> [!example] 
> - `id` = `"5f2afa21-7668-4db3-b949-159c8a7ab31b"`
> - `competitionId` = `"5f2afa21-7668-4db3-b949-159c8a7ab31c"`
> - `name` = `"Red Commission"`
> - `isApproved` = `false`
> - `currentWineSampleId` = `"5f2afa21-7668-4db3-b949-159c8a7ab31d"`
> - `startedAt` = `1387321861`
> - `endedAt` = `1387321862`