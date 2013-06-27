---
layout: post
title: "AngularJS talk from 33rd Degree Conference"
date: 2013-06-27 15:52
comments: true
categories: slides, AngularJS
---

On 15th of March this year I gave a talk about AngularJS on the 33rd Degree Conference. Instead of trying to introduce the building blocks of AngularJS like I did a couple of times before, this time I tried to concentrate on the things that I consider the biggest advantages as compared to other JS MVC frameworks.

## Two-way data binding

Something that really changed the way I write JS code is two-way data binding. It removes a ton of boilerplate code from your applications and allows you to completely remove the coupling of your controllers to DOM. Honestly, I can't imagine using a framework that does not have this feature any more.

## AngularJS is POJO

The code you write in AngularJS is mostly written in Plain Old JavaScript, without the need to inherit from any framework base classes or introducing a custom object model. This gives you a lot of freedom when it comes to modeling your domain, saving you from putting most of your logic on your "model classes", which many other solutions seem to default to. The fact that pretty much all the code you write is Plain Old JavaScript Objects also helps a lot with testability, since isolating yourself from the framework is much easier if your are not inheriting from classes you don't own.

## Slides

<iframe class="slides" src="/slides/embedder.html#/slides/angular33/" frameborder="0">
</iframe>

Unfortunately the talk was not recorded, so there's no video, but I hope the slides alone will give you some idea what I talked about.
