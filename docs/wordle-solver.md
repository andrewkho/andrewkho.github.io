---
layout: page
title: Wordle Solving with Deep Reinforcement Learning
permalink: /wordle-solver/
---

Jan 2022

[github](https://github.com/andrewkho/wordle-solver)

Like a lot of people, I've been playing the daily Wordle challenges since I found out about them. 
Even my mom's been sharing her daily scores in my family's group chat. 

## TL;DR

If you don't want to read all this nonsense, the approach that worked for me was A2C (Advantage Actor Critic), a policy gradient method.
I used a staged training approach where I progressively trained the network to solve harder and harder problems and warmstarted each time it saw a more difficult problem.
I also designed a neural net where instead of learning the full space of ~13k possible discrete actions, the model only needed to learn 130 outputs.

I also tried Deep-Q learning (DQN), but it didn't seem to work for me on the full sized problem.
I started to experiment with Soft-Actor Critic (SAC) before I realized A2C with bootstrapped training was going to work on the full problem size.

## How to play Wordle

Just in case you haven't played [Wordle](https://www.powerlanguage.co.uk/wordle/), it's a game where you have to guess a 5 letter word within 6 tries.
After each guess, the game will tell you which letters are in the correct spot, which are in the wrong spot, and which don't appear in the word at all.

<center><img src="../assets/wordle-example.png" width="130" height="200" /></center>

One of the big challenges is that your guesses _must_ be a valid word; i.e. you can't just enter characters that you want to try out.
It's quite a challenging game the first few times you play!
Anecdotally though, most people are able to figure out the words within 3-5 guesses.

I'd just finished replaying [Advent of Code](https://adventofcode.com/) so I could [learn some golang](https://github.com/andrewkho/aoc2021/), and was looking for another excuse to play with go. 

## Existing solutions

I thought maybe a Wordle solver would be the way to go.
I was curious about what other people have been trying, and one of the first hits to come up was this [post on a minimax method](https://towardsdatascience.com/automatic-wordle-solving-a305954b746e).
The approach described there is to choose the word that minimzes the worst case scenario.
The author tested it's worst-case performance as 5 guesses, which is extremely good for such a simple heuristic!
However, in my experiments with it, it often took more guesses than I took, and I'm quite the notice.

## Reinforcement Learning

After scratching my golang itch and reimplementing the minimax in go, I figured the next thing I should try to do is incorporate some sort of information on how frequenty certain words are.
In the Minimax problem there are ~13k possible words to guess, and the best one in a given situation probably maximizes some expectation, which is exactly what [reinforcement learning](https://en.wikipedia.org/wiki/Reinforcement_learning) is trying to do. 

My first thought was to come up with some clever state vector and then do dynamic programming to figure out the optimal strategy.
Unfortunately I wasn't able to come up with a tractable problem. 
The rough math looked like: blah blah blah

## Deep Learning
Enter model-based approaches, where you try to approximate the Q-function with some parameters.





#####

As I learned on [this post](https://leancrew.com/all-this/2022/01/wordle-letters/) the actual problem is somewhat simpler, in that, at the time of this post, there are only 2315 words that can be used as answers to wordle, although there are still 13k allowed words.

___
[Back to projects page](/)


