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

## Reasons to storm
In this article we are going explore four of the outcomes you may be seeking in doing an event storm. 

### Discover problems in a process
The first outcome we are going to explore is trying to find problem areas, or pain points, in a process.  This would normally be done as a part of Discovery and Framing, a scoping, or some other event where we are trying to rapidly understand a system or process, and determine areas that could be explored further for possible software solutions. Swift, is a discovery framework that can be employed to do this level of modelling.  It does provide other tools to get a more detailed model in a shorter period of time, but we will cover that a bit later. We will typically break out two tools for this level of modelling, events and pain-points.

#### Events 

* Events are always recorded in the past tense
* Events are always the result of some *Command* that triggered its occurrence
* Event payloads should only consist of what's changed in an aggregate from its prior state
* Events are recorded in time sequence

#### Pain points, hot spots

When dealing with existing processes and systems, pain points and hotspots are highlighted as areas that need to be addressed. These could be used to prioritize areas in the existing system that should be worked on first. Essentially build a heat map of which problem areas will provide the most amount of value with the least amount of effort. Then prioritize other areas to establish a backlog to address these areas.

### Discover the language of a process

#### Definitions
The collection of these stickies will ultimately become your glossary.  These capture important words or phrases along with their definition.  An important thing to note here is it is possible, if the system is large enough, to have the same word or phrase with two different definitions.  The 

### Model a process

#### Commands

* Commands are directly mapped to some Process that affects the business
* Commands trigger some use case which result in an *Event* being recorded
* Commands can be triggered by multiple *Actors*: a user or group of users, a scheduled task or timer, a *Policy* 

#### External Systems

#### Aggregates

* Aggregates are the nouns in the business process and systems
* Aggregates are affected by recording *Events* in a time series
* A time series of *Events* can be used to show state of the Aggegate at any point in time
* A *Bounded Context* typically is wrapped an Aggregate
* A *Bounded Context* governs what/who can affect that Aggregate

#### Policy

#### Read model

#### Actors (Users, time, )

### Architecting a system

#### Recognizing bounded contexts

#### Establishing contracts

## Additional Tools that could be employed

## Summing up