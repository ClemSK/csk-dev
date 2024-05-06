---
title: "Property Analytics - pt. 1"
date: 2024-02-23T08:18:50Z
draft: true
tags:
- scraping
- property data
- data viz
---

# Project setup

I'm working on property data analytics dashboard called [London Property Pulse](https://github.com/ClemSK/london_property_pulse/). It's a Go project with real-world application to provide insights and enable action(s). 
It's designed to be a companion tool to those provided by property listing sites to show relative value of the property in an area as well as city-wide trends. 

### Tech

As mentioned I'm going to be using Go and tools in the ecosystem.

- [Go](https://go.dev/)
    - Upgraded net/http router from 1.22
    - [Air](https://github.com/cosmtrek/air): Live reload utility
    - [Colly](https://github.com/gocolly/colly): Scraping framework
    - [Rod](https://github.com/go-rod/rod): Browser automation
- [Postgres](https://www.postgresql.org/)
    - [SQLC](https://docs.sqlc.dev/en/stable/index.html#): SQL compiler
    - [Goose](https://github.com/pressly/goose): Migration tool
- [Docker](https://www.docker.com/): Containeriser
- [Go-echarts](https://github.com/go-echarts/go-echarts): Chart library
- [HTMX](https://htmx.org/): HTML as hypertext
    <!-- - [Book](https://hypermedia.systems/book/contents/) -->
- [Templ](https://templ.guide): Templating language
- [Makefile](https://www.alexedwards.net/blog/a-time-saving-makefile-for-your-go-projects)

### Seting up the project

- Go version: 1.22
- CI / CD
    - GitHub actions
- Internal modules
- [Makefile](https://www.alexedwards.net/blog/a-time-saving-makefile-for-your-go-projects)
- Setting up HTMX + Templ

### Parts of the project

- get property data
- search for property
- display visuals
- filtering data

    



