---
layout: single
title: "Intro to Reinforcement Learning"
excerpt: "Model development using TensorFlow in preparation for my thesis"
date: 2025-06-14
collection: projects
header:
    teaser: assets/images/rl_practice/mountain_cart_good.gif
order: 4
---

### Development of DQN using TensorFlow NN's

As preparation for my thesis, RL for a reservoir computing, I completed this project to solidify my understanding of deep reinforcement learning. This project was done directly after reading and studying corresponding chapters of "AI: A Modern Approach".

Since DQN is the first algorithm I am to implement in my thesis, I focused on a standard implementation of the algorithm using TensorFlow for the neural network. Based on the paper, I implemented experience replay buffers, epsilon-greedy action selection and batch gradient descent. Additionally, I added reward shaping, intermediate model saving, and Weights & Biases integration.

### Results

I tested my model on OpenAI Gymnasium's Cart Pole and Mountain Car. I successfully played each, achieving strong learning performance with my algorithm. 

**Cart Pole**
{% include figure image_path="assets/images/rl_practice/cartpole_500_drift.gif" alt="cart pole gif" 
%}

{% include figure image_path="assets/images/rl_practice/cartpole_500_drift_plot.png" alt="cart pole png" 
%}

**Mountain Car**
{% include figure image_path="assets/images/rl_practice/mountain_cart_good.gif" alt="mountain car gif" 
%}

{% include figure image_path="assets/images/rl_practice/mountain_cart_good.png" alt="mountain car png" 
%}