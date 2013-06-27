---
layout: post
title: "Bogus talk at DRUG"
date: 2013-06-27 18:41
comments: true
categories: [slides, bogus, krug, ruby]
---

On the 20th of May this year I gave a talk about [Bogus][bogus] on [DRUG][drug].

About a week earlier I gave a [longer talk with the same title][previous] on KRUG, but even though I kept the title, the second presentation couldn't be more different from the previous one. While the talk on KRUG was more encyclopedic and giving an overview of most of the Bogus's features, on DRUG I decided to go with a more storyline-oriented approach to give people a better idea of what Bogus's motivation is and why it really is a new generation mocking framework.

Event though this presentation does not fully describe the features of Bogus, it does show a few testing/implementation patterns and the problems you might run into (or avoid) with them.

I'm much happier with this presentation than the previous one, mainly because while safe stubbing is a very useful feature, it is also important to realize that the design of your system can have a huge impact on the reliability of your test suite.

<iframe class="slides" src="/slides/embedder.html#/slides/bogus-drug/" frameborder="0"></iframe>

[bogus]: https://github.com/psyho/bogus/
[drug]: http://drug.org.pl
[previous]: /blog/2013/06/27/bogus-talk-at-krug/
