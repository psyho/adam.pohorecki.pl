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
In this series of blog posts I am going to describe them and list the advantages and disadvantages of each approach.

<!--more-->

## What are Services?

So far I have already used the term "services" twice in this article, without defining what I mean by that.
It's time to amend that.

Eric Evans in his book [Domain Driven Design][ddd_book] introduced several types of building blocks for applications:

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

The visionaries of that age were not happy with this approach so they thought that making the models do the heavy lifting, while the controllers just call the right method on the model and ensure that the right thing gets rendered.
This approach was given a name "Skinny Controllers, Fat Models".

Initially, the models were pretty skinny, but over time they accumulated more and more fat.
You see, every time a developer added a feature to the system, he would ask himself a question: "Where should I put this code?" and guess what? 
The code usually ended up stuffed on the bottom of the poor model's class.
Soon enough, the models most central to the application's domain, like User would span hundreds or thousands of lines of code and have dozens of methods.

Once you find the same method defined multiple times in the same 2k LOC-long file, you know you hit the rock bottom. The 3000 "unit" tests that take 30 minutes to run don't help the feeling of accomplishment either.

As more and more quick-and-dirty startups written in Rails matured, the nagging feeling that we have fattened our models beyond the point of recovery crept into many a developer heart.
Thankfully, with Ruby and Rails becoming more mainstream, the community is now more diverse than ever and ideas such as DDD, which are more widely adopted in statically typed languages like Java or C#, have proliferated into the Ruby world.

As we became more open to the idea of separating our business logic from the Rails framework, many different approaches started popping up.
In this series of blog posts, I am going to try and present the various approaches known to me, with their strengths and weaknesses as I see them.

## The framework

I am going to create a simple Rails application using each of the approaches below and post the highlights of each approach as a separate blog post.
The entire applications will be available as branches of the [psyho/services-on-rails][repo] repository on GitHub.

The application will be a simple typing game with following features:

* the players will be able to take a typing test that measures CPM/WPM/accuracy
* the players scores will be saved and presented as a nice graph on the home page
* the players high scores will be listed on the home page
* the players will be able to register and login to the application
* the players will be able to add quotes to be used in typing tests

The JavaScript part of the application will stay the same, and only the API implementation will actually change.

## Skinny Controllers, Fat Models

This is the traditional approach to writing Rails applications.
The application will have most or all of it's code in models and controllers, with no dependency injection or isolated tests.

## Functional Style

This is the approach that I picked up watching the awesome [Destroy All Software][das] screencast series by Gary Bernhardt.
I call it functional because it separates the business logic into modules or classes that mostly have just a single public class method, which makes them essentially global functions, while the model remains rather anemic.
This approach does not use any kind of dependency injection as well.

## Objects-on-Rails style

This is the approach that I observed in the great [Objects on Rails][oorails] book by Avdi Grimm.
It is truer to the letter of Domain Driven Design, because it keeps a lot of the business logic within the models, while still separating certain things into separate classes.
This approach uses dependency injection for tests, while the production code pulls it's dependencies from the environment.

## Data Context Interaction

This is an intriguing approach that originated from the book [Lean Architecture][lean_arch].
In this approach you separate your business logic into use cases and roles.
Within a use case (which is called a Context), you enhance the relevant Data with needed roles (Interactions) and then execute one or more methods, which came from the roles on the data.
DCI allows you to split your business logic into small, testable chunks, and enhances the readability of the use case "algorithm", by making it live within a context.
It does not need to build a graph of objects, so it does not need DI, however injecting the needed roles into data is quite similar to manual dependency injection.

## Manual Dependency Injection aka Dependor

Last but not least, the approach which is my personal favorite.
It combines the functional service layer found in the Destroy All Software approach, with dependency injection, which means that you end up with small classes, with usually just a single public method, but the objects in the system are decoupled from each other.
Using a few simple helpers, which I released as a gem called [Dependor][dependor], this approach can make your code both terse and highly configurable.

[ddd_book]: http://domaindrivendesign.org/books/evans_2003
[repo]: https://github.com/psyho/services-on-rails
[das]: http://destroyallsoftware.com
[oorails]: http://objectsonrails.com/
[lean_arch]: http://www.leansoftwarearchitecture.com/
[dependor]: https://github.com/psyho/dependor
