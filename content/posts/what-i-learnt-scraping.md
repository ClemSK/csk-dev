---
title: 'What I Learnt Scraping'
date: 2024-07-28T15:08:12+01:00
draft: true
tags:
  - colly
  - go
  - scraping
  - problem solving
---

## Scraping property data with Go and Colly

I'm making the project that motivate me to start coding: building a property scraper which renders analytics.

For those that are interested, here is the tech I'm using:

- [Go](https://go.dev/): version 1.22
  - Router: Upgraded net/http router from 1.22 instead of [Chi](https://github.com/go-chi/chi)
  - [Air](https://github.com/cosmtrek/air): Live reload utility
  - [Colly](https://github.com/gocolly/colly): Scraping framework
- [Postgres](https://www.postgresql.org/): Relational database
  - [SQLC](https://docs.sqlc.dev/en/stable/index.html#): SQL compiler
  - [Goose](https://github.com/pressly/goose): Migration tool
- [Docker](https://www.docker.com/): Containeriser
- [Caddy](https://caddyserver.com/): Multipurpose server, used for reverse proxy
- [Go-echarts](https://github.com/go-echarts/go-echarts): Chart library
- [Templ](https://templ.guide): Templating tool for Go
- [HTMX](https://htmx.org/): HTML as hypertext
- [GoatCounter](https://github.com/arp242/goatcounter): Simple, privacy compliant web analytics

- start scruffy and then write clean code
- scraping property data
- selectors
- scraping listing and details pages
- writing to a JSON file
- concurrency
- rate limiting
- scraping by postcode
- large data set but only shows 1000 at a time

## Build it twice

I gave myself permission to build scruffy and the write clean code. There can be premature optimisation by creating abstractions or separations before you know what you're building. In the beginning all the code was in one file and being called from the main.go function.

Scraping is a useful skill to have, and knowing how to do it in Go was a chance to use go and solve some fun problems along the way.
