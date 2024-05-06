---
title: "Cloudflare Netlify Deployment"
date: 2024-02-20T08:39:29Z
draft: true
tags:
- deployments
---

# Cloudflare DNS + Netlify host

- netlify hosting
- cloudflare dns
- netlify config file 


I went with Netlify as it makes it very simple to deploy a static site and has a useful CLI for future deployments. 


### Chose and buy a domain - the fun part! 
When making a personal site it's best to chose a site name that contains your name or a variation of it. It should reflect what you do / who you are. That said, it's your choice. 

I chose Cloudflare as it's a reputable and cost effective domain name registrar that also has all the services that I could ever need.

### Netlify config

Before deploying to Netlify I recommend installing the CLI by running 
- `npm install netlify-cli -g` 
- checking the install: `netlify`
- and authenticating using: `netlify login`


This part is critical and will make your site error / not render if not configured. 
Mentioned in both the Hugo and Netlify docs, you need to add a `netlify.toml` file:

```
[build]
  command = "hugo --gc --minify"
  functions = "netlify/functions"
  publish = "public"

[build.environment]
  HUGO_VERSION = "0.122.0"

```
Hugo command param explanation:
- `--gc`: enable to run some cleanup tasks (remove unused cache files) after the build
- `--minify`: minify any supported output format (HTML, XML etc.)

To populate `HUGO_VERSION` run `hugo  version` to find your current version. There will be extra bits but just use the version number and ignore everything else. 

### Netlify hosting

### Cloudflare dns


### Links
[Hugo docs: Host on Netlify](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/)
[Netlify docs: Hugo on Netlify](https://docs.netlify.com/integrations/frameworks/hugo/)
[Configure Cloudflare DNS to Work with Netlify](https://stevepolito.design/blog/configure-cloudflare-dns-to-work-with-netlify)
[Cloudflare DNS + Netlify host - Jake Trent](https://jaketrent.com/post/cloudflare-dns-netlify-host/)

