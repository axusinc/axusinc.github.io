---
title: Exceptions were improved
draft: false
tags:
  - axusid
---
As you know, exceptions (errors) in [[AXUS™ ID]] consist of:
- `className` -- In fact name of the exception class in SDKs corresponding to the error.
- `message` -- Description of the exception.
- and other fields...
Until now, there were many general exception classes like **[[Variation]].IsInvalidException** and many exceptions used these general classes specifying the detailed reason in `message` field. But that was not convenient, cause to handle different exceptions in the same context (**e.g.,** [[Variation]] class) differently, the only way to classify exceptions was to filter them by `message` field, which can be changed very frequently.

So we have improved the exceptions system and now **each** exception has it's own class that inherits (in SDKs) more general exception classes (e.g., **[[Variation]].IsInvalidException** class). Due to that you can handle exceptions as preciselly as you want.

> [!example]
> When creating a new user via `createCredentials()` method using [[AXUS™ ID Java-Kotlin Raw SDK]], you can just handle all exceptions regarding [[Username]] equally:
> ```kotlin
> try {
> 	val credentials = rawClient.createCredentials(
> 		Username("example.com"), 
> 		Password("12345678") // Bad password btw!
> 	)
> 	println("Success! Your AUID is ${credentials.auid.value}")
> } catch(e: Username.IsIncorrectException) {
> 	println("Oh no! An error with the username occured: ${e.message}")
> }
> ```
> **...or** you can handle them separately:
> ```kotlin
> try {
> 	...
> } catch(e: Username.LengthIsIncorrectException) {
> 	println("Your username is too long :(")
> } catch(e: Username.IsNumberException) {
> 	println("Unfortunely number usernames are reserved :(")
> } catch(...) {
> 	...
> } ...
> ```

Also general exceptions like **[[Variation]].IsInvalidException** were split into:
- **[[Variation]].IsInvalidException** -- Throwed when the object with these parameters cannot exist at all. **For example,** accumulated length of [[First Name]] and [[Last Name]] specified in a [[Variation]] is more than `28`.
- **[[Variation]].IsIncorrectException** -- Throwed when the object with these parameters can exist but in current context it is not allowed to use the parameters. **For example,** the requested [[Variation]] (**e.g.,** by **[[Variation]].Id**) is not available.