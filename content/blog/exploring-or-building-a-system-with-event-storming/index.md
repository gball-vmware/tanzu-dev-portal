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

## Tools of event storming

## Reasons to storm

### Discover problems in a process

#### Events 

* Events are always recoreded in the past tense
* Events are always the result of some *Command* that triggered its occurrance
* Events record only what's changed in an aggregate from it's prior state
* Events are recorded in time sequence

#### Pain points, hot spots

When dealing with existing processes and systems, pain points and hotspots are highlighted as areas that need to be addressed. These could be used to prioritize areas in the existing system that should be worked on first. Essentially build a heat map of which problem areas will provide the most amount of value with the least amount of effort. Then prioritize other areas to establish a backlog to address these areas.

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

## Summing up