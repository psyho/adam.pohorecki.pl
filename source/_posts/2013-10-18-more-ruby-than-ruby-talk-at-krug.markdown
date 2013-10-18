---
layout: post
title: "More Ruby than Ruby talk at KRUG"
date: 2013-10-18 00:02
comments: true
categories: [slides, ruby, clojure, krug]
---

A few days ago a tweet reminded me about a talk I gave on the 6th of August on [KRUG][krug]:

<blockquote><p>One trend I&#39;m observing is a lot of rubyists being fed up with messy ruby ecosystem are getting excited or even switch to clojure.</p>&mdash; Piotr Solnica (@_solnic_) <a href="https://twitter.com/_solnic_/statuses/390163528138899456">October 15, 2013</a></blockquote>

## I &#10084; Ruby

I have been programming in Ruby professionally for over four years now. When I was starting out, there were probably mere dozens of Ruby programmers in Kraków. Compared being one of the thousands of Java developers, programming Ruby felt almost exotic.

Not that long ago, being a Ruby programmer meant being on the bleeding edge of web development. You had to deal with immature and unstable libraries, crappy deployment options and IDEs that didn't offer much more than syntax highlighting. On the other hand, it also meant working with smarter than average people, who were drawn to this technology not just because it was new, but also because it was in many ways superior to the other options out there. I loved it.

A couple of years have passed and I still love Ruby. I actually love it so much, that I called my dog Ruby. However, the times have changed. Rubyland is no longer the domain of adventurous and industrious early adopters. Ruby is now mature, stable and "enterprise-ready". Somewhere along the way Ruby has become the responsible choice of a language for building web apps.

Let's face it: Ruby is a good language to know right now. The jobs are plentiful and well-payed, and the technology is still relatively modern, but progressively more safe and boring. The days of exciting and unpredictable Ruby are almost over, and soon I'll only be able to like it as a friend.

## I &#10084; Clojure

I have come across this LISP on the JVM quite a while ago, but having had pretty bad experiences with Common LISP at my university, I never had much interest in it until in May of 2012 I came across a [presentation given at RailsConf][simplicity-matters] by Clojure's creator, Rich Hickey.

I am a huge believer in Single Responsibility Principle. Most of my classes have one public method. I tend to avoid inheritance and heavily favor composition and delegation. Unfortunately, a language like Ruby punishes you for coding in this style - your small classes end up being split amongst hundreds of files and often wrapping a function in a class seems like an overhead.

Watching that video made me realize that maybe I should look into functional programming languages. After all, functions are smaller units of composition, and they are easier to combine. I watched a bunch of other Hickey's presentations and I got hooked on Clojure.

Compared to other functional languages like Scala or Haskell, Clojure, as a dynamically typed language, was much more up my alley (in the dispute between static typing vs TDD, I stand strongly behind TDD). It also appealed to me more than Erlang, since I mostly work on web apps, and Clojure seems to do better with those.

## Clojure > Ruby

I read a couple of books about Clojure, started playing with the language and I fell in love with it.

Let's start with the fact, that Clojure is perfectly capable of expressing pretty much everything that Ruby can, most of the time just as concisely. This in itself is not much of an achievement, but factor into that the syntax of both languages. Even I could write a parser for Clojure. Do you know anyone who could write a parser for Ruby? Clojure's syntax is the perfect marriage of power and simplicity.

Clojure has real namespaces, where Ruby only has modules. Clojure's keywords can be namespaced as well. It avoids Ruby's method naming problems (like when two libraries adding a method with the same name to a class like String of Array). Clojure has ClojureScript. Clojure is well suited for multithreaded programming. Clojure has macros. Clojure is faster...

I believe that this is a great time to get into Clojure programming. The ecosystem is mature enough that you can find libraries to do pretty much everything you need (even if they are not overly polished). The people in the community are above the average, because they have learned Clojure, not because Clojure programmers are in demand, but because they wanted to. There are also plenty of books, screencasts and other resources to learn Clojure from.

Uncle Bob called Clojure "The Last Programming Language". I would settle for "The Next Big Thing". Dig in while it's hot:)

## Slides

Unfortunately the presentation was not recorded, so all I have are these slides:

<iframe class="slides" src="/slides/embedder.html#/slides/clojure-krug/" frameborder="0"></iframe>

[krug]: http://www.meetup.com/Krakow-Ruby-Users-Group/
[simplicity-matters]: http://www.youtube.com/watch?v=rI8tNMsozo0
