---
title: "Deep Learning for Coders"
date: 2025-07-09T09:24:10+01:00
draft: false
tags:
- ML
- Deep learning
- Python
---
tl;dr
- AI for everyone: pretty good as a foundation.
- Deep learning for coders: Wow!

In 2025, with so many AI products coming out, it seems like a good idea to properly learn what it's all about and how I can build my own models and integrate them into a project. 

In my initial foray into learning ML, I found that the `AI for Everyone` course by Andrew NG was a good intro to the topic and ideas at a very high level. 
It's a good basis for understanding the lay of the land and the different areas to dive into.

However, my mind was blown when I started the `Practical deep learning for coders` by Jeremy Howard. In the first 2 lessons (around 2-3 hours of setup and then running through the lessons) I was able to:
- Train an image classifier
- Learn how to host and deploy a model via API

Given that I have no experience in ML, I was extremly impressed that I could see a clear path to implementing features that use Deep Learning in a very short space of time.

In my project, I want to generate reports based on London property data and combine it with a rating of room finishings. Manually this would be very slow and time consuming, but with ML it would put the product in a class of its own (if I manage to create an accurate model).

It also paves the way to implementing other types of ML features into my application using tabular and text data.

To use these models I'm going to add a Python server to my setup. There are several reasons for this:
- My primary server is written in Go, which does not have a developed ML ecosystem
- I want to be able to call the models via API to either call them directly or from my Go server
- As I alluded to above, I might implement further ML features, so having a dedicated service to handle this makes sense rather than just calling python file here and there
- Go is fast and more than capable of serious data crunching, however, there might be cases where it makes sense to leverage libraries in the python ecosystem
- Python was my first programming language, with it I learnt to OOP, the main algorithms + data structures and did a few data/scraping projects with it so it's nice to use it again!

I've put a short list of resources that I've found helpful while getting started, I hope you find them helpful too.

Exciting times ahead!

### Resources
- Concepts / non-technical course
    - [AI for Everyone - DeepLearning.AI](https://www.deeplearning.ai/courses/ai-for-everyone/)
        - Free course
- Overview of ML
    - [The Hundred-Page Machine Learning Book by Andriy Burkov](https://github.com/tirthajyoti/Papers-Literature-ML-DL-RL-AI/blob/master/General-Machine-Learning/The%20Hundred-Page%20Machine%20Learning%20Book%20by%20Andriy%20Burkov/Links%20to%20read%20the%20chapters%20online.md)
        - GitHub book with PDF  available
- Implementing an ML model
    - [Practical Deep Learning for Coders - Practical Deep Learning](https://course.fast.ai/)
- Productising / integrating AI into products
    - [Deep Learning Courses - Full Stack Deep Learning](https://fullstackdeeplearning.com/course/)
- Professionalising your workflow, end-to-end
  - [Building Machine Learning Powered Applications](https://www.oreilly.com/library/view/building-machine-learning/9781492045106/)
- Textbook
    - [An Introduction to Statistical Learning](https://www.statlearning.com/)
        - free download available with python examples


