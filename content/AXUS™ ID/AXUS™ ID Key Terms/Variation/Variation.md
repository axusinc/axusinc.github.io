---
title: Variation
draft: false
tags:
  - axusid
---
Why do we introduced [[Variation]]s in [[AXUS™ ID]]? Because people frequently create **many accounts** **e.g.,** in **Google**, **Instagram**, etc.: one for personal life, another for work, another for games for example and so on.
So [[Variation]]s are going to allow users to separate work & personal life while still using only one account (which is much more convenient than many different accounts). 
With [[Variation]]s you can have separate avatars, names, statuses, content in social networks, etc.

> [!example]
> [[likespro]] can have the following variations:
> 1. **Personal**
> 	- [[First Name]] **Like Pro**
> 	- [[Last Name]] **\*not set\***
> 	- [[Status]] **Making the world better**
> 	- [[Description]] **CEO of AXUS™, Enterpreneur, Diverse developer, Author of Articles, Competitive programmer, etc.**
> 	- Location ([[Custom Geolocation]]) **\*not set\***
> 	- More formal posts, **LinkedIn** style
> 2. **Real life**
> 	- [[First Name]] **Andrij Mykhalko**
> 	- [[Last Name]] **\*not set\***
> 	- [[Status]] **\*the same\***
> 	- [[Description]] **\*similar but with more real life details (e.g., born place, university, etc).\***
> 	- Location ([[Custom Geolocation]]) **\*the same\***
> 	- Posts about every-day thoughts and life, **Instagram** style
> 3. **Gaming**
> 	- [[First Name]] **Play Games**
> 	- [[Last Name]] **\*not set\***
> 	- [[Status]] **Trying to kill final boss in X game**
> 	- [[Description]] **Welcome to Play Games! Here we play Minecraft, Fortnite, etc.**
> 	- Location ([[Custom Geolocation]]) **\*the same\***
> 	- All posts related to games & games streaming/videos themselves.

For more convenience, all users have a default [[Variation]] (they can change it any time)
## Structure
- `id` -- **Id** of the [[Variation]], an unchangeable [UUIDv4](https://en.wikipedia.org/wiki/Universally_unique_identifier).
- `auid` -- [[AUID]] of the user, an unchangeable `64-bit` `integer`.
- `icon` -- **Icon** (it's [[Image.Id]] in [[HyperCDN™]]) of the [[Variation]], a changeable `nullable` `string`. Currently not supported and therefore is always set to `NULL`. **Icon** is the [[Variation]]'s symbol on transparent background and is used next to [[Variation]] name in **UI**.
- `firstName` -- [[First Name]] of the user in this [[Variation]], a changeable `nullable` `string`.
- `lastName` -- [[Last Name]] of the user in this [[Variation]], a changeable `nullable` `string`.
- `status` -- Short text status of the user (**e.g.,** what is he doing now), a changeable `nullable` `string`.
- `description` -- Text description of the user (**e.g.,** who is he in a few words), a changeable `nullable` `string`.
- `location` -- Public location of the user, a changeable `nullable` [[Custom Geolocation]]. Currently not supported and therefore is always set to `NULL`.
- `createdAt` -- time when the [[Variation]] was created, an unchangeable [[Timestamp]]. Usually default [[Variation]] creates on the first request to get the user's default [[Variation]], so it is **lazy generated**. Other [[Variation]]s are created on demand.