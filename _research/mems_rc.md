---
layout: single
title: "RL for MEMS-RC"
excerpt: "Reinforcement Learning for a MEMS-based Reservoir Computer"
date: 2025-11-26
collection: research
header:
    teaser: assets/images/mems_rc/panda_reward_wandb_cropped.png
order: 1
---

(in progress)

## The Project

My master’s thesis at Cal Poly is the implementation of reinforcement learning algorithms on a simulated MEMS-based reservoir computer. 

On the reinforcement side, my work focuses on implementing RC-specific versions of two algorithms: DeepMind’s DQN, a value-based approach, and OpenAI’s PPO, a policy gradient approach. Due to the linear readout layer, these algorithms follow the ANN approach closely; however, RC PPO requires less coupling of the actor and critic objective functions, hopefully leading to more efficient training. The successful implementation of each of these algorithms proves the compatibility of RL algorithms with MEMS RC hardware.

On the RC side, I am investigating the effects of RC hyperparameters on a model’s learning performance. Utilizing tools like Ray Tune, I am running investigative grid searches, comparing the effects of each hyperparameter. While this work is currently in progress, I have found significant learning differences between different input signal periods and the randomization of the masking function.

## Some Background

This is a short introduction into what the main topics of my thesis are: reservoir computing (specifically on a MEMS device) and reinforcement learning.

### Reservoir Computing
Reservoir computing (RC), a subset of the neuromorphic genre, uses a highly dynamic system to represent a sparsely connected neural net. One choice of a ‘reservoir’ is a Micro-Electro-Mechanical System (MEMS) device. By inputting a specific voltage signal, measuring the MEMS state at specific time points, and then feeding the outputs into a linear readout layer, we are left with a form of a recurrent neural network. 

A major part of the system is the masking function. This encodes the inputs or states of our task in out voltage signal. As of now, the masking function is a random telegraph signal, either -1 to 1. There is a unique masking function to encode each input from our system. After our inputs are applied to their masking functions, we superimpose these signals and input the resultant to our MEMS system. The period of our masking function is called theta, which is normalized to be nondimensional. At each theta, we read the state of our MEMS state to get a 'neuron' reading. We have N neurons in our reservoir meaning that our masking signal is N*theta long. Each neuron has a equivelant weight and bias before as part of the readout layer. After the readout is applied to our neuron outputs, we have our reservoir computer output.

For example, lets use the classic cart pole game, an inverted pendulum on a cart balancing task where we know the position and velocity of the cart and the angular position and velocity of the pendulum. The two possible actions are to push the cart left or right. For our RC system, we take the 4 state observations, apply each of their masking functions, and input them into our MEMS system. We take our neuron readings, scale them with the readout layer, and use the output as our control signal.

### Reinforcement Learning