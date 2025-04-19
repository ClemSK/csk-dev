---
title: "Launching a Site"
date: 2025-01-05T11:17:51Z
draft: false
tags:
- launching
- site
- mvp
---

Yesterday [London Property Pulse](https://london-property-pulse.com) went live. Launching is a euphoric and satisfying moment where you feel 'Hooray, I'm on the Internet 🎉'!

Here's to launching early 🍻

The site is definitely far from ready, with bare-bone BE and FE but this way I can see how my changes affect the site's performance and build in public. It also helps my motivation: now it's real and in the world 🌍. 

## Learnings
### Getting familiar with Linux
I'm trying something new by hosting on a virtual private server (VPS) - aka Linux box in the cloud - and had a few things to learn along the way but got there in about a day. While I'm familiar with unix environments, working without the bells and whistles of my comfy and configured environment was a bit of a shock but relatively easy to work. 

### Exceeding low resources is way to easy
I started using the most basic plan my VPS provider offered but quickly found that it was running out of memory as I was trying to build my docker images. In the end I bumped up the spec twice to get the performance necessary to run my setup. As I'm going to be using a lot data the additional disk space was welcome but I thought that might come later in the process than it did. It was an eye opener that my setup couldn't run properly on 1GB of memory, however performant.

### Responsibility for being in control
'Nice I control everything! ..oh, I have to manage what now?!'

Part of launching this site was to learn how to manage the details of hosting a site, saving costs, getting in the weeds of devops and so far ✅. Though, I have had to configure ports, permissions, miscellaneous configurations and a firewall. I now understand that managed services charge more, but honestly for a little more hassle and significantly smaller bill it's worth it. The flip side is that I now have more freedom about what happens on my server than the likes of Vercel, Railway and Netlify would expose to me. 

### DNS
This time around it was much easier to hook up my domain to my IP address and register it with the registrar. Last time I struggled with configuration of my domain with Netlify and Cloudflare name servers. Maybe I'm getting better, or just following standard practice better 🤷‍♂️. The harder part of the launch of my site was getting my pipeline to work correctly. 

### Docker and pipeline secrets + automating builds
As good practice I have my pipeline build and push my code to my container registry and then use the new image to deploy to my VPS. However, I found working with GitHub and Docker a bit of a faff. I worked it out in the end but it took about a million runs of the pipeline and debugging the statements before getting a clean run and deploying to the VPS. Part of the issue was the lack of power of the VPS making it impossible to run the code. I had to restart the VPS several times when it would even refuse SSH connections. 

## Architecture
I watched a [great talk from Amazon on YT](https://www.youtube.com/watch?v=kKjm4ehYiMs) which outlines realistic architectures at different scales and studied the [system design primer](https://github.com/donnemartin/system-design-primer). They helped guide me to not over-engineer my current approach but also prepare for scale. 

There are 4 parts to the setup: 1. Docker, 2. Caddy, 3. Go, 4. React, 5.Postgres

### Containerisation with Docker
The main benefits of Docker are consistent environments and easy replication. Due to this, it means I can have secure builds that can be deployed and scaled to multiple instances as needed. It would also make it easy to move to anther cloud provider. 

### Caddy web server
Caddy acts as the front-door to the site and works in a monorepo or micro-services contexts. I set up the web server to act as a reverse proxy, file server and rate-limiter, with capabilities for load-balancing and Caddy made that a breeze.

### Go backend
I chose Go mostly because I like it but it's also performant, resource efficient, has great concurrency and can be deployed in Linux, Mac and Windows environments. 

### React frontend
React was mostly a fallback and could have been another framework but is fast to get started and has a large ecosystem to leverage. I tried using Templ but found that it was too limiting and slowing me down for trivial things that would be easy to do in a React context. Ultimately, I used React because if Templ was challenging to use and there was very little code, what would it be like when there was complexity and a lot more code? Moreover, Templ's state management story was not for me. In this situation I picked a larger bundle size, JS/TS, speed, and a broader ecosystem over server rendering interactions. 

### Postgres database 
Choosing between Postgres and MongoDB as a starting option, my view is that Postgres is the sensible default. I like the structure of types and querying power of a relational DB. That being said, my application is going to be read heavy and I will be performing a number of queries on the data so a relational DB makes more sense at this point.

## Now the real work starts
I felt a need to launch the site, now it is I can start on core feature work that will bring the site to life. 🚀 


