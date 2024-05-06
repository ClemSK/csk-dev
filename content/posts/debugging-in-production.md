---
title: 'Debugging in Production'
date: 2024-04-25T08:21:24+01:00
draft: false
tags:
  - rethinking
  - debugging
---

**Challenge: for a week, don't use a debugger and only use the tools you can use to debug in production.**

- What did you notice?
- What workflow changes did you make to get to the same level of productivity as before?

### Why abandon the debugger?

The debugger has it's place, but it can be a crutch to crafting well-thought-out software.

As useful a tool as the debugger is, not being able to use a debugger reveals a lot about coding practices and processes.

Not being able to use a debugger becomes a forcing function, you need to have the right infrastructure and processes in place to catch bugs early:

- Great error handling and logging
- Rigorous tests
- Code reviews
- Good CI/CD practices

Even then, bugs will still slip into production.

I think main outcomes of out of this exercise are:

1. Enhanced tooling and processes for catching bugs
   Layering human and and automated means adds varying ways of cleaning up code
2. Upgrading production debugging capabilities
   You don't want to realise that there is poor logging when the prod environment is down
3. Better team understanding of how to debug in production

If we were to stop using the debugger today, what tools would you use to improve code quality?

- https://lemire.me/blog/2016/06/21/i-do-not-use-a-debugger/
