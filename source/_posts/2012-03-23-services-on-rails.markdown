---
layout: post
title: "Services on Rails"
date: 2012-03-23 17:02
comments: true
categories: OOP dependency-injection services rails ruby
---

In the recent months we have seen the Ruby and Rails community shift from the largely procedural into more object-oriented paradigm of writing applications.
It is no longer fashionable to put all your application's logic into the model, just as before it stopped being acceptable to inflate views and controllers with business logic.

We, as a community, have finally rediscovered the Single Responsibility Principle and embraced the isolated unit tests.
For the first time in years "Fast Rails Tests" are no longer an oxymoron.

With the advent of OOP in Rails came a number of styles of implementing the service layer.
In this blog post I am going to describe them and list the advantages and disadvantages of each approach.

<!--more-->

## What are Services?

So far I have already used the term "services" twice in this article, without defining what I mean by that.
It's time to amend that.

Eric Evans in his book ["Domain Driven Design"][ddd_book] introduced several types of building blocks for applications:

#### Value Objects

Value Objects are identified by their state.
Examples of value objects are strings, numbers, dates and so on.

#### Entities

Entities are identified by their identity, which could for example be the `id` attribute.
Two entities that have the same `id`, but different state, are considered representations of the same "object" in different points in time.

#### Services

Services are operations that do not belong conceptually to any object.
They are usually stateless.
Most of the business logic of an application is usually contained within services.

#### Aggregates

Aggregates are essentially a specialized kind of entity that group several entities under a root entity and guard the access to the "inner" entities to ensure consistency of changes made to them.

#### Repositories

Repository is a kind of service that is used to persist and retrieve domain objects.

#### Factories

Factory is a kind of service that is used to create domain objects.

The first three types I listed are in my opinion the most important ones, mostly because the others can be viewed as specialized types of entities or services.

Typically when testing your application you should never use test doubles (stubs/mocks/fakes etc.) in place of value objects and very rarely in place of entities, but you should feel free to stub and mock services.

## The evolution of Rails applications

In the beginning there was nothing... Well, maybe not nothing, but certainly a huge pile of spaghetti code.
The logic of our Rails applications was scattered all over the place: the views, the controllers and the models.
Then we realized that the views are no place for the logic, so we moved it into our controllers.

In those dark days the controller actions would span dozens of lines of code reaching freely into model objects and doing unseemly things to ActiveRecord.

The visionaries of that age were not happy 

## Skinny Controllers, Fat Models


## Functional Style

## Objects-on-Rails style

## Manual Dependency Injection

## Dependor

[ddd_book]: http://domaindrivendesign.org/books/evans_2003
