---
layout: page
title: Matrix Factorization from Scratch
permalink: /matrix-factorization/
---

June 2018

[github link](https://github.com/andrewkho/netflix-play)

I was reading [Recommender Systems, Agarrwal 2016](https://www.amazon.com/Recommender-Systems-Textbook-Charu-Aggarwal/dp/3319296574) and wanted to get hands on with some of the algorithms described in the book.
I think I tried a few of the methods based on clustering and nearest neighbours but they didn't scale to the Netflix dataset size.
What ended up working well was straight up Matrix Factorization, with stochastic gradient descent as the solver.

At the time I was primarily a Java programmer and I wanted to get up to speed with Python. Python was slow for my tastes, so I rewrote a lot of it in Cython which helped a bunch. 
I was able to do a reasonable amount of hyperparameter tuning on my desktop CPU.

___
[Back to projects page](/)


