---
title: 'Cursed Dev Words'
date: 2024-04-24T22:31:31+01:00
draft: false
tags:
  - development
  - communication
---

When developing there are words that are ambiguous when describing a problem.

One of my pet peeves is when I hear someone say these cursed words: _'it was working'_

The problem is that it's fuzzy and does not help identify causes. Logically it's simplistic - yes, in the last PR is was probably working and now with the new PR it's broken. It should be expected that over time enough code changes will cause breakages.

The real questions to ask are:

- What is the new observed behavior?
- What triggered it?
- When was it last seen functioning following the current or former specs?

Better questions are:

- What do we have in the logs / traces? (if available)
- When was the last time a services had an outage?

I think the best way to not arrive at a situation where we hear ourselves say _'why is it not working'_ is to cultivate better questions.

While situations and tech stacks change, having a mental toolkit of questions to ask yourself and others when things go wrong can be a shortcut to getting a real solution to the issue.
