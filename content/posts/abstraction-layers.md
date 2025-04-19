---
title: 'Abstraction Layers'
date: 2024-12-08T00:20:07Z
draft: true
tags:
  - abstraction-layers
---

## Simple vs control

- I skipped on D3.js because it was too complicated for my needs opting instead for go-echarts: a beautiful and configurable charting library with lines, bars, heatmap, and pie charts and then some.
- Early in the experimentation process, I found I was not able to move a slider bar which can be changed in echarts but not in go-echarts and ruining the esthetics of my chart. It was not a limitation of the charting library but a limitation of implementation by the library writer. As such it was time to go a level deeper and ditch go-echarts and use echarts directly.
- Though one of my main aims was to limit the amount of javascript I wrote to a minimum, I think there was no way around it and I'm now considering my options. I got a new mvp working with the new approach, so it's just a matter of thinking about what is practical and sustainable. If possible I might add typescript but likely, in the beginning I'm just going to use js in script tags.
- I'm going to be displaying property data so my needs are on the simpler side, but there is scope for growth with echarts. Still, I wanted to be able to make them look exactly the way I wanted.

## When simple isn't good enough

- go to the underlying level to get the necessary ability to achieve your goals
