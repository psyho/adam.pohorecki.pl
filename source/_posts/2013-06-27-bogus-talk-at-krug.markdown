---
layout: post
title: "Bogus talk at KRUG"
date: 2013-06-27 18:18
comments: true
categories: [slides, bogus, krug, ruby]
---

On the 14th of May this year I gave a talk about [Bogus][bogus], my mocking library, at the local [Ruby Users Group][krug].

## Bogus

Bogus is a mocking library that I've been working on for over a year now. It's what I like to call a "new generation" mocking library, as opposed to gems like Mocha, RR or rspec-mocks, which represent the "old generation".

What makes the new generation of mocking libraries different is the fact that it emphasizes safety. The new generation libraries won't let you stub methods that don't exist or with a wrong number of arguments. When creating test doubles, the new generation also tries to preserve the interface of a real collaborator, so that you don't run into problems with API drift.

Bogus implements all of the aforementioned safety features and more. Our goal is to give you a much higher degree of confidence in your (isolated) unit tests and to speed up your builds by letting you get rid of unneeded integration tests.

## Slides

<iframe class="slides" src="/slides/embedder.html#/slides/bogus-krug/" frameborder="0"></iframe>

## Video

<iframe width="600" height="338" src="//www.youtube.com/embed/XGT66XRXCwk?rel=0" frameborder="0" allowfullscreen></iframe>

[bogus]: https://github.com/psyho/bogus/
[krug]: http://www.meetup.com/Krakow-Ruby-Users-Group/
