---
title: Exploring or architecting a system with event storming
description: 
date: '2023-01-25'
slug: event-storming-methods
tags:
- architecture
- "domain driven design"
  team:
- Dan Frey
- Greg Ball
---

## A quick reminder on event storming
Event storming is a method by which a team of people can model a business process.  This process may be as simple as making a peanut and jelly sandwich or as complex as managing multi-million dollar bank transactions.  At its foundation, it's all about modeling something, but the degree to which we model it can produce different outcomes.  Also, the tools that we employ while executing the event storm, can get us a higher fidelity model to help produce those outcomes. In this blog we will explore how we can use the event storming to achieve different things, and the tools needed to do that.

## Tools of event storming
Anyone who as been at an event storm knows that, by the end, there is a massive pile of stickies of all the colors of the rainbow.  Each of these stickies represents something different in the process.  On their own, they arent all that useful, but when placed on a board, wall, or window in a particular order, you end up with a modeled process that can help you make huge decisions.  We will cover many of these stickies, we will call them tools, throughout this article.  Each building on the last to provide a higher fidelity model, and perhaps, driving you to a different outcome. 

**To the sandwich-storm!:**

### Events 
Events are the foundational tool of event storming, thus the name.  No matter the purpose of the event storm, you are at least going to do these.  By writing events and placing them on the board in timeline order, we can see the things that happen in the system, and the temporal relationship between them.  Participants of the event storm will spend a considerable amount of time writing these events down and determining where they go in the continuum. Here are some additional characteristics of events.  

* Events are always recorded in the past tense
* Events are always the result of some *Command* that triggered its occurrence
* Event payloads should only consist of what's changed in an aggregate from its prior state
* Events are recorded in time sequence

**To the sandwich-storm!:** Events in the process of making a sandwich might be, "peanut butter purchased", "bread retrieved from package", and "peanut butter spread".

### Pain points, hot spots
When dealing with existing processes and systems, pain points and hotspots are highlighted as areas that need to be addressed. These could be used to prioritize areas in the existing system that should be worked on first. Essentially build a heat map of which problem areas will provide the most amount of value with the least amount of effort. Then prioritize other areas to establish a backlog to address these areas.

**To the sandwich-storm!:** A pain points or hot spots might be the point at which we must change from spreading peanut butter, to spreading jelly.  Since this can lead to complication in cleaning or swapping utensils, or worse yet, tainting the jelly with peanut butter or vise versa.

### Definitions
The collection of these stickies will ultimately become your glossary.  These capture important words or phrases along with their definition.  An important thing to note here is it is possible, if the system is large enough, to have the same word or phrase with two different definitions.  Typically, this means that there are multiple bounded contexts in your application, which may result in multiple services.  Use this as a data point to make decisions, not as something to be ignored.

**To the sandwich-storm!:** Some important definitions to capture here might be "butter (verb)" and "peanut butter (noun)".  It may be simple in this use case, however these types of distinctions happen in business all the time.  If for whatever reason I shortened peanut butter, to "butter" when I talked about it, it would create an ambiutiy with the verb butter which may be used to identify the spreading of the peanut butter.  These types of ambiguities are crucial to eliminate.

### Commands
Commands are things I request the process.  Unlike events, that have already happened and cannot be changed or revoked, commands can have 2 or more responses.  In the simplest form, a command would result in an event indicating success, or an event indicating failure.  

* Commands are directly mapped to some Process that affects the business
* Commands trigger some use case which result in an *Event* being recorded
* Commands can be triggered by multiple *Actors*: a user or group of users, a scheduled task or timer, a *Policy* 

**To the sandwich-storm!:** One command in this process would be to command our peanut butter jar for peanut butter by sticking a knife in it.  One resultant event for that might be "peanut butter retrieved" while the other might be "peanut butter retrieval failed" if the jar was actually empty.  

### External Systems
Depicting external systems on a event storm helps to define boundaries of event storm by abstracting some processes all together. 

**To the sandwich-storm!:** We may choose to make the grocery store an external system.  If we didn't and wanted to create a complete model, we would need to model how the grocery store worked from getting a cart, to adding things to that cart, to checking out and everything in between.  By making it an external system we only need to care about the commands going into the external system "buy peanut butter" and the events coming out of it "peanut butter purchased".

### Aggregates

* Aggregates are the nouns in the business process and systems
* Aggregates are affected by recording *Events* in a time series
* A time series of *Events* can be used to show state of the Aggegate at any point in time
* A *Bounded Context* typically is wrapped an Aggregate
* A *Bounded Context* governs what/who can affect that Aggregate

**To the sandwich-storm!:**

### Policy
Policies are manual or automated actions or sets of actions that are repeatable.  A common way to identify policies is by saying if-this-then-that.  Given the same event input or trigger, the same command or commands would be invoked.  

**To the sandwich-storm!:** If the unimaginable happens, and you get a "peanut butter retrieval failed" event as depicted earlier.  There is something we must always do in order to rectify the situation, and that is to "purchase peanut butter".  Therefor the policy (or if-this-then-that) will be if "peanut butter retrieval failed"(event) then "purchase peanut butter"(command).

### Read model

**To the sandwich-storm!:**

### Actors (Users, time, )

**To the sandwich-storm!:**

### Bounded contexts

**To the sandwich-storm!:**

### Additional Tools that could be employed
#### SNAP Analysis

#### BORIS

## Reasons to storm
In this article we are going explore four of the outcomes you may be seeking in doing an event storm. 

### Discover problems in a process
**Tools Generally Employed:** Events, pain points

The first outcome we are going to explore is trying to find problem areas, or pain points, in a process.  This would normally be done as a part of Discovery and Framing, a scoping, or some other event where we are trying to rapidly understand a system or process, and determine areas that could be explored further for possible software solutions. Swift, is a discovery framework that can be employed to do this level of modelling.  It does provide other tools to get a more detailed model in a shorter period of time, but we will cover that a bit later. We will typically break out two tools for this level of modelling, events and pain-points.

### Discover the language of a process
**Tools Generally Employed:** Events, pain points, definitions

The next outcome you may be seeking is a slight variation of the one before, and it's in order to map out the [ubiquitous language](https://tanzu.vmware.com/developer/blog/ubiquitous-language/) of a business domain or set of domains.  Generally 

### Model a process
**Tools Generally Employed:** Events, pain points, definitions, commands, policies, read models, actors

Modeling a process 

### Architecting a system
**Tools Generally Employed:** Events, pain points, definitions, commands, policies, read models, actors, bounded contexts

## Summing up