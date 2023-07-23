---
title: "Change is the enemy of perfect design"
seoTitle: "Change is the enemy of perfect design"
datePublished: Sun Jul 23 2023 20:17:35 GMT+0000 (Coordinated Universal Time)
cuid: clkfvrwk0000a09l85pxzbt0v
slug: change-is-the-enemy-of-perfect-design
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690142930525/2be52eed-e862-4f79-8861-000b3f209190.png
tags: go, architecture, beginners, infrastructure, system-design

---

Haven't written in a while but it never harms to blurt out what's going on in my mind once in a while. Today let's take a look at how we have reached this stage of bleeding-edge technology but at the same time have eradicated means of out-of-the-box approaches as we evolved. Don't get what I'm trying to tell you? Just hold on a bit and all of it would be crystal clear.  
Starting with the big question:

### What exactly is a system design? Why do we need one?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1690142562380/e50f6181-181b-4855-aec3-af1cace1fc14.png align="center")

Well... This one takes us far back, to the era of cranky servers and hard-wired server architecture, quite literally. In these modern times, all that intimidating server wirings and stuff are now available at the fingertips of a modern developer with layers of abstraction and encapsulation but this is not how the story ends. You see, we have been evolving our designs and architectural patterns in ways that would suit most of the cases.

Say, at some point in history, many developers started to build a product like an e-commerce website. All of a sudden, there was a surge of developers using the same type of design patterns. Eventually, this resulted in companies taking the chance to build technologies which would cater for all of the "basic" needs of the system developers. For instance, provide some sort of plug-and-play services and server configurations. Now imagine this as a layer of abstraction, when companies started to provide such services to the folks who developed in environments that were being used in most of the scenarios.

Now imagine this type of evolution tuned exponentially to bring us to the present times. Now we have products like AWS, Azure, Shopify, Stripe, PayPal and many others. There is a ton of features and functionalities which are provided to us by such products via layers of abstraction. Abstractions, happening on such low and high levels, are providing faster development, reduced complexity, and enhanced scalability. At this stage, to build an application that is truly general in its approach, a simple E-commerce website for example, there won't be a lot of thought to be put. There are tools and services that will bring such an application to life in maybe just some hours and be able to scale it to whatever required numbers.

BUT.

What if I want to build something totally out of the box? Something completely different from what the developers are used to build? Let's say we require to build something low-level, that serves our custom needs and requires unique architectural choices. And here, folks, enter the long-lived approach of system design in its true essence. At this point, probably most of that "evolved" services and tools are of no use. Pretty possible that now you might have to go back to dealing with the tangled server's era and build your way up to achieve whatever type of functionality you seek.

To build something this out of the box, it is, when you think of system design and architectural patterns in their real sense.

\=============================================================

Now, as you might have been able to observe, the more sophisticated and efficient a type of design gets, the lesser is room for change or development or any kind of out-of-the-box Crazy stuff.

A design is something that is a solution to a particular problem at some given time. Let's take our old classic enemy of scaling up and the complexities it carries.

![](https://hackernoon.com/hn-images/1*pFpJjVDfN8X1Dp-_PvzKdQ.png align="center")

## A Simple Problem

I'll sight a really basic example and get things going.

How about I give you a task to write down a list of your favourite movies. The problem at hand: writing a list of your favourite movies. A probable solution: get a pen, a paper, and jot it down(nice and neat).

Now I ask you to do the same for your family members. The same problem but with increased candidates. Same solution: get a pen, a paper, and tediously jot it down(a bit cramped maybe).

Now go do the same task for everyone present in a hall containing 20 people. At this point, you may keep checking the ink of your pen and carry a spare one, might need a bunch of sheets or even a notebook.

Let's evolve the problem even more, now it's a wedding where 100 guests are present and you are required to make out the most favourite movie of the crowd there. A probable solution: you get a few other people to help you with the same task of jotting the list of 20 people at once, this would require 5 individuals at the same rate. Congrats we are now able to do dumb analytics over a bunch of people.

What if we had to do the same thing for a thousand individuals living in a particular area? At this point, you'll probably take the help of the technology around, make a web app comprising of a form, host it and let everyone fill it on their own. Makes everything pretty simple right? NO, not yet.

Scale up to 10,000 individuals in a town now. At this number, a small-time server could easily crash. Here many factors come into play like load balancing, database optimizations, API gateways, scalable infra, monitoring, security, etc. Each solution was idle for its own highly specific problem, the problem changes slightly, and you gotta change your design.

Now if I say that change is the enemy of perfect design, does it make more sense?

### A Subjective Approach from a wider view

Let's take another interesting perspective. Most of the legacy systems from the early 2000s are completely built over the concepts of OOP. Many of them have even overused and literally abused such concepts in their code bases making a newbie dev's life a hell.

This doesn't exactly lie under system design but is a nice example of what I'm trying to state.

Over the years, the concepts of OOP have been used and overused to such an extent that many times even an experienced developer would struggle to figure out the code base. OOP isn't a worse programming paradigm as such but as the code bases grow bigger and bigger, as things get more and more abstract and inherited under the same project itself, it becomes too hard for a new developer on the team to figure out references, calls and the actual functionality. And this problem is only going to grow bigger and wilder.

This is not exactly a "technical" problem but more of a philosophical and subjective statement. After all, the Production is more about maintaining the code than pushing new lines, isn't it? Maybe the new buzz of OOP was a good choice for projects where the bases weren't as big as they are now, and maybe now we need to get back to the OG composition and coupling approach, which is also gaining popularity slowly as languages like GO and Rust make their way up.

![](https://programmerhumor.io/wp-content/uploads/2023/03/programmerhumor-io-programming-memes-e6100f23c780906.jpg align="center")

I'll make sure to elaborate on this thought in an upcoming blog as it would be out of scope for this article. Be sure to drop your thoughts down here and look out for an upcoming post along the lines of such programming paradigms.

But as you could make out from the above statements that the problem is just not limited to servers, clouds and databases but even to the level of the approach we take to write our code.

### Wrapping it up...

There are numerous problems out there in this world and I just listed a few, a few solutions and a few scenarios of approach. Be it scaling up a solution from one to 10,000 using different approaches or even the approach we use for writing our code, as time passes, the solution evolves with the problem, it is impossible to stick to one kind of design forever and hence, the statement, change is the enemy of perfect design.