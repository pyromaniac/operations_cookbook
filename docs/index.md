---
layout: page
title: "Intro"
permalink: "/"
---

# Intro

In this GIT book I'll try to reflect my experience and knowledge as a collection of recepies and approaches that everyone is free to follow in their applications. The goal is to make the Rails application world a bit better and more unified place.

Ruby on Rails framework did a great job for application unification. Using Rails means that anyone with Rails experience can come to the project and know right away where to look in order to proceed with the project's evolution.

Ruby on Rails is a great framework to kick-start whatever project but when your project grows it becomes more and more difficult to support and modify code written in the rails way. Models coupled with the domain logic getting possessed with nomeruous contradicting callbacks, conditional validations, virtual fields and domain logic.

It is a time to separate the concerns. While it is difficult to do in an existing application, it is not impossible. The process might be slow thought (depending on the amount of resources) and the idea is to make the target goal clear to all the participants by using a framework.

A consequence of [CQS](https://en.wikipedia.org/wiki/Command%E2%80%93query_separation) claim is that there are only 2 kind of methods. This is also true for any abstraction level.

In OOP on the classes level there is separation of data and behavior, which is actually forced (I believe) by people who were heavily affected by the FP paradigm. While OPP was designed specifically to blend in both in a single object, it, again, depends on the level of abstraction. And from my experience, domain is something that is actually better to design keeping [SoC](https://en.wikipedia.org/wiki/Separation_of_concerns) in mind.

On an application level there is [CQRS](https://microservices.io/patterns/data/cqrs.html), which works not only on the microservices' but also in the API level for REST and GraphQL. This principle in general is a way to follow [SRP](https://en.wikipedia.org/wiki/Single-responsibility_principle).

Assuming that we have a REST application in hands. It might be GraphQl API as well, there are 2 general kinds of HTTP requests: GET and POST, queries and mutations, receiving data, sending data. Every HTTP request is handled by a piece of code. So, keeping CQS in mind, there are 2 kinds of handlres: Query and Command.

While Query pattern is simple to imlement in Rails and it doesn't get really complex. Just fetch all the data from DB, don't forget to solve N+1 and that's it. To make the code testable, we can extract a separate class (it can be called ViewModel or ReadModel), which accepts some query params and returns all the requested data.

Command part is a bit trickier. And this is exactly what is this book about: implementing Command pattern in Rails application, quirks, tips and tricks.
