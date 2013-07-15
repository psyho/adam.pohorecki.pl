---
layout: post
title: "PPPPP talk at KRUG"
date: 2013-07-15 20:06
comments: true
categories: [slides, ppppp, krug]
---

On the 9th of July this year I gave a talk about Ping-Pong Pomodoro Pair Programming on [KRUG][krug].

## Ping-Pong Pomodoro Pair-Programming

{% img right /images/ppppp/pair-programming.png %}

I always wanted to do pair programming, but every time I tried, I failed to get much benefit out of it and I walked away tired and frustrated. I didn't really know what I was doing wrong. Every time I raised questions at conferences about how to succeed at pair programming I didn't get any good answers.

The problem is that pair programming is not that easy to get right. If you want to be successful doing it, you need to be at least twice as performant (for some definition of performance) as a single person. You also need to avoid burnout that comes with working harder than you would by yourself.

## Pomodoro

{% img left /images/ppppp/pomodoro.png %}

Thankfully I kept trying and at one point when programming with [Rudy][wrozka] we started doing [Pomodoro Technique][pomodoro] in addition to pair programming. 

Pomodoro is a personal productivity technique that says you should concentrate on a single task for 25 minutes and than take a 5 minute break afterwards, with a longer, 20 minute break every 4 pomodoros.

It turned out that by using Pomodoro we not only got all the advantages of that technique (focus, work rythm, daily planning) but also **we avoided the burnout that has followed pair programming** for me before.

## Ping-Pong

{% img right /images/ppppp/red-green-refactor.png %}

Once we realized that frequent switching during coding keeps us both fully concentrated, we also added [Ping-Pong][ping-pong] pair switching technique to the mix.

Ping-pong is a natural extension of TDD to pair programming. You switch at the keyboard for every part of the red-green-refactor cycle, with the first person writing a failing test, the second making it pass and the first person refactoring.

In traditional pair programming you switch at the keyboard every couple of minutes, but what I've found is that it is very easy for one person to keep typing for much longer than that. What I've also found is that **after being away from the keyboard for about ten minutes your mind starts to drift away** and you lose your focus on the code being written. With ping-pong we make sure that both of us are fully engaged and focused on the code that we are writing.

## The Presentation

If you want to learn more about PPPPP, I recommend that you check out the full presentation below:

<iframe width="600" height="338" src="//www.youtube.com/embed/Qc_tehYzxI0?rel=0" frameborder="0" allowfullscreen></iframe>

<script async class="speakerdeck-embed" data-id="08530b10cb7601305ae10eeaf12a37c4" data-ratio="1.33333333333333" src="//speakerdeck.com/assets/embed.js"></script>

[krug]: http://www.meetup.com/Krakow-Ruby-Users-Group/
[wrozka]: https://github.com/wrozka
[pomodoro]: http://www.pomodorotechnique.com/
[ping-pong]: http://c2.com/cgi/wiki?PairProgrammingPingPongPattern
