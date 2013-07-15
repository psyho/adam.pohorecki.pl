---
layout: post
title: "PPPPP talk at DRUG"
date: 2013-06-27 20:10
comments: true
categories: 
  - PPPPP
  - slides
  - drug
  - pair-programming
---

Along with the [presentation about Bogus on DRUG][bogus-talk] I also gave a lightning talk about the way I work every day with [Rudy][rudy].

Most people I know don't pair program at all or only do it occasionally and for a couple of hours or days at a time. We spend pretty much 100% of our time at work pair-programming. Heck, we actually have only one computer between us, so we can't do it any other way, even if we wanted to.

While pair-programming itself is not really that hard, maintaining that way of working over an extended period of time is not trivial. We use a certain mix of techniques that allows us to do it and we call it PPPPP, which stands for Ping-Pong Pomodoro Pair-Programming.

## Pair Programming

Many Extreme Programming techniques have managed to achieve mass adoption, but pair programming is not one of them. Most programmers I know use TDD, do continuous integration and work in iterations, but pair programming somehow does not have the same appeal.

Pair programming promotes shared code ownership, improves code quality and helps in knowledge sharing within a team. It gives you a line-by-line code review as you work, which lets you avoid making mistakes instead of correcting them after the fact. It even simplifies project management, because a team that does pair programming has half as many tasks in progress as a team that doesn't.

Beneficial as it is, pair programming is also hard work, in a quite literal sense. Things that you take for granted, like taking breaks when you feel like it, checking email and RSS, spending an hour reading documentation, etc. are all gone. Pair programming forces you to concentrate on the task at hand pretty much the whole day, and that can be very tiring.

## Pomodoro

Pomodoro is a technique where you concentrate for 25 minutes on a single task and nothing else (no checking email, IM, etc.). After every such iteration you get a 5 minute break. After every four iterations you get a longer break. You start each day by planning and estimating the tasks for the day and end with a short retrospective.

We use Pomodoro because of the rhythm it introduces. We no longer have to ask each other to stop working when we feel tired, because we know that in a couple of minutes we will have a few minutes to rest. It helps us maintain concentration during the day, because we only have to keep it for less than half an hour at a time. In short, it keeps us from getting burned out.

## Ping-Pong

Once you start pair programming you will observe that once you spend more than a couple of minutes away from keyboard, you concentration flutters. To combat that we use a pairing technique called Ping-Pong.

When you write your code using TDD, you go through a well-known red-green-refactor cycle. In Ping-Pong, person A writes the failing test, then person B makes it pass and finally person A performs refactoring. Next cycle starts with person B, and so on and so forth.

This technique helps us maintain concentration and improves shared code ownership, because there's never any code that "you wrote and I just watched".

## Slides

I apologize for the quality of the slides, but they were supposed to be more of a discussion starter than means of conveying information. Hopefully the ones from a talk I'm giving this month at KRUG will be more useful.

**EDIT:**

The [slides and video from my PPPPP presentation at KRUG][new-slides] are already available. Check them out if you are interested in learning more about this topic.

<iframe class="slides" src="/slides/embedder.html#/slides/ppppp-drug/" frameborder="0"></iframe>

[bogus-talk]: /blog/2013/06/27/bogus-talk-at-drug/
[rudy]: https://github.com/wrozka
[new-slides]: /blog/2013/07/15/ppppp-talk-at-krug/
