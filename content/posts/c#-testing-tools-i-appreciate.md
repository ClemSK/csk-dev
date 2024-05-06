---
title: 'C# Testing Tools I Appreciate'
date: 2024-05-06T15:19:40+01:00
draft: true
tags:
  - testing
  - CI/CD
---

This is purely backend - frontend testing is a totally different beast.

The list:

- [XUnit](https://xunit.net/docs/getting-started/netcore/cmdline): unit testing library
- [Fluent Assertions](https://fluentassertions.com/introduction): specify the expected outcome of a TDD or BDD-style unit test
- [Moq](https://github.com/devlooped/moq/): mocking library
- [Testcontainers](https://testcontainers.com/): framework for providing light, throwaway instances of DBs, message
  brokers, etc. that can run in a Docker container.

### XUnit

The basis of unit tests

### Fluent Assertions

Helps with writing more readable TDD style tests

### Moq

For helping with mocking objects in unit tests

### Testcontainers

Makes integration testing that much easier, helping by creating separate instances of DBs to not pollute the dev environment and integrates well with CI/CD.
