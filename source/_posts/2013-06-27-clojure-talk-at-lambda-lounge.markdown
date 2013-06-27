---
layout: post
title: "Clojure talk at Lambda Lounge"
date: 2013-06-27 17:17
comments: true
categories:
  - slides
  - clojure
  - lamda lounge
  - functional programming
---

On the 28th of March this year I gave a talk about [Clojure][clojure] on the inaugural meeting of [Kraków's Lambda Lounge][lambda-lounge].

With the questions from the audience this talk run way too long - over an hour and a half. I definitely tried to cram too much content into the presentation - from protocols and multimethods, through macros, first-order functions, immutability to concurrency constructs. Most of those things really deserve a presentation of their own.

## Protocols and Multimethods

If you ever used an Object-Oriented language like Ruby, you are probably familiar with the concept of polymorphism. Since Clojure is a functional language and it's primary unit of composition is a function, you'd think that by using it you have to sacrifice polymorphic dispatch, but you don't. 

Even better, Clojure's polymorphism is much more advanced than that of Ruby, and allows you to dispatch on arbitrary properties of any number of function arguments. Defining type relationships is also more powerful, since they can be defined on a per-function basis (if needed of course). Function-first approach also saves us the headaches of naming conflicts that could happen when including multiple modules into a class in Ruby.


## Functional Programming

Functional programming is all the rage right now, but many people seem to think that it's all about using first order functions. Once you get to use it however, you suddenly realize that the thing that makes the biggest difference is state management and immutability. 

Immutability not only helps in multithreaded environments, but it also makes reasoning about code much easier, because any state change made very explicit by forcing functions to return updated data. This approach to handling state also helps testability by separating your code into the functional core (super easy to test), which you can unit test to your heart's content and imperative shell (interaction with the external world, state management), which you can easily integration test, because there are only a couple of paths possible through it.

## Concurrency Constructs

I spent a good deal of time in my presentation showing a laundry list of Clojure's concurrency constructs, which certainly are plentiful and seem like a very nice addition to java.util.concurrent. So far I only used atoms, but I don't really deal with multithreaded apps much, hopefully one day that will change:)

## Slides

<iframe class="slides" src="/slides/embedder.html#/slides/clojure-lambda/" frameborder="0">
</iframe>

The presentation unfortunately wasn't recorded on video.

[clojure]: http://clojure.org/
[lambda-lounge]: http://www.meetup.com/Lambda-Lounge-Krakow/
