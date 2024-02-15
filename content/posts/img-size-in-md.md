---
title: "Img Size in Md"
date: 2024-02-14T09:06:35Z
draft: false
tags:
- writing
- styles
---

# Styling images in markdown

I'll refer to the StackOverflow answer on [changing image size in `md`](https://stackoverflow.com/questions/14675913/changing-image-size-in-markdown). 

The simplest and most free of dependencies is just to use a CSS class in a CSS file to style the image. 

This removes the need for markdown processors etc. that would (with more code) end up in the same place. 

In Hugo this would mean adding the styles to the `assets` folder and writing them up this way: `img[alt=drawing] { width: 200px; }`. 



