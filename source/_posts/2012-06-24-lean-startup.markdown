---
layout: post
title: "Lean Startup"
date: 2012-06-24 02:25
comments: true
categories: lean-startup tdd
---

{% img left /images/blog/lean-startup.png Lean Startup cover %}

I recently read the ["Lean Startup" book by Eric Ries][book] which I can recommend to anyone involved in software development, not just people working with technology startups, like the title suggests.

The book describes a process, which can be used to make innovation more manageable and directed using the Lean Manufacturing principles combined with metrics-driven-development.
It is written with entrepreneurs in mind, but it also touches on topics such as Continuous Deployment and automated testing, which are important to me.

<!--more-->

## The problem solved by Lean Startup movement

In my career, I have seen a certain mistake repeated too many times.
I call this mistake "feature overload".
It happens when a product, based on someone's arbitrary decision, is gradually extended with features that don't necessarily add value, until it's so slow and bloated that it has to be rewritten or fails altogether.

If you are a programmer, you might recognize this smell from code.
The principle of avoiding this kind of mistakes is called [YAGNI][yagni] (You Ain't Gonna Need It).

BDD advises that we write our User Stories in form "**In order to...**, As a ..., I want to...".
This first clause ensures, that the features we implement, are actually ones that are needed to improve the product.

Lean Startup takes this idea much further by applying scientific principles.
It obligates us to measure how the users react, and based on that, validate whether the feature actually brings value or not.
If a feature does not bring us closer to the goal, then it should be removed.

## Extending the Definition of Done (DoD)

Typically, a Definition of Done in Scrum looks something like this:

* implemented
* passed the code review
* tested
* accepted by the client
* deployed

Lean startup appends another item to that definition: "validated".
This means that for every feature deployed you would run a [split test][split-test] with the feature enabled and disabled and based on the metrics gathered during the experiment, you would consider whether this feature is worth keeping or not.

It is worth noting that unvalidated features count toward the Work in Progress limit in Kanban, so this limits your development speed to how fast you can deploy and validate features, since only a limited number of split tests can usually be run at once.

## Continuous Deployment

As you can probably see already, projects that take advantage of the Lean Startup methodology are ideal candidates for Continuous Delivery (or Deployment):

* If you need to a/b test everything, then you must have feature switches implemented.
* If the process requires you to deploy often, you can't probably just do that at the end of iteration.

## TDD and Lean Startup

Ron Jeffries wrote a blog post a couple of years ago about [why you can't do iterative development without writing automated tests][test-needed].
It essentially states that if you want to release often, you need to test everything just as often, and that's impossible to do that by hand.

Obviously, if you want to deploy each time a feature is implemented, this becomes even harder, so you need automated tests even more.

Ries in his book does agree with the fact that you need an extensive automated test suite, however he considers automated *unit* tests a from of waste and advocates writing end to end tests instead.

The opinion that isolated unit tests are of limited use is often heard amongst people who don't practice TDD.
I believe in the opposite: isolated unit tests are the most valuable tests you can write, while the end-to-end tests are the ones that provide the least value.

### Tests are about feedback

Imagine you have a test suite that takes an hour to run. 
How often would you run it during your regular development?
Would you even run it locally? 
I know I would not.

Now imagine your test suite takes 15 seconds to run (1-2s for unit tests and the rest for integration tests).
Would you run it locally? 
Maybe even each time you save a file?

If you tests are slow, nobody runs them except for your CI server.
End to end tests tend to depend on the structure of your markup and often are brittle and unstable.

Fast tests give you confidence to change and refactor your code, and if you follow one simple rule of mocking (**don't mock what you don't own**), you will rarely fall into the trap of mocking too much.
When unit tests fail, they point you almost exactly to where the failure occurred, which reduces the time spent debugging.

I strongly believe that TDD is a technique that eliminates waste and makes rapid change possible. I think it should be a core practice for every lean startup.

## Cohort Analysis

Cohort Analysis is a technique that I first read about in the Lean Startup book.
It is optimized to give you feedback on how the changes you introduce modify your user's behavior.

For example, let's say you implemented a feature that awards users certain amount of points when they visit the site each day.
Your hypothesis is that this will increase the user retention.

To validate your hypothesis you run a split test with the new feature enabled for some portion of the new users arriving at your website.
You measure how many users visit your site, register and how many of the registered has returned to the site at least 3 times.

At the end of the experiment, you present your metrics as a percentage of the overall number of visitors in the given segment.
In theory, the percentage of users who register should not vary significantly, but the percentage of users returning to the site should increase.

I really like how lean startup forces you to define your acceptance criteria in terms of things that can actually be measured.

## The 5 Whys

Another interesting technique, which I first encountered in Eric Ries's book is ["The 5 Whys Technique"][5whys].

It is a technique for determining the root cause of a problem by asking the question "Why...?" (kind of like children do) five times in a row.
You do this every time something goes wrong (like when you deploy not working software to production, or when you go over the WIP limit on a Kanban board).
Once you get answers to the 5 questions, you can apply an amount of effort proportional to the scale of the problem, to each of the problems that came up as answers to the questions.
This way you get to improve and make your process more resistant to failure, but you also make sure that you don't spend too much time on things that don't happen often or are not too important.

## Final remarks

Agile development methodologies tell us to embrace change, which is a great step forward comparing to the old waterfall/change-request days.
However they do not give us a way to judge which features are more important, and which are not.
This is a problem, because it involves a lot of guesswork and politics.

Lean startup gives us a way of making feature decisions based on hard data and facilitates building the right product, not just a product the right way.

[book]: http://theleanstartup.com/book
[yagni]: http://en.wikipedia.org/wiki/You_ain't_gonna_need_it
[split-test]: http://en.wikipedia.org/wiki/A/B_testing
[test-needed]: http://xprogramming.com/blog/what-is-really-essential/
[5whys]: http://en.wikipedia.org/wiki/5_Whys
