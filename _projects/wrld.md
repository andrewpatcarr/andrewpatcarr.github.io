---
layout: single
title: "WRLD"
excerpt: "An affordable bipedal droid for testing reinforcement learning-based control and computer vision models"
date: 2025-09-27
collection: projects
header:
    teaser: assets/images/wrld/in_dirt_right.png
order: 1
---


{% include figure image_path="assets\images\wrld\in_dirt_right.png" alt="in_dirt_right"
%}

# Inspiration

I learned about Disney Imagineering's [BDX droid](https://la.disneyresearch.com/wp-content/uploads/BD_X_paper.pdf) in August of 2024 and loved the look of their droids movement and was very interested in the RL control. 

When I started my design, I wasn't thinking or directly trying to remake what they had, but it obviously subconsciously directing my design. I mainly focused on a design resembling my friend's lego BD-1 while trying to make it creatively my own.

I've been a Star Wars fan from as long as I can remember so this type of creation always lingers in the back of my mind. Since my thesis involves RL, it seems like the right time to start a project like this.  

# Project

An affordable (forced lol) bipedal droid for testing reinforcement learning-based control and computer vision models. This project specifically will push my full stack design abilities for a mechatronic system, especially one running AI on a microprocessor. 

As of 09/27/2025, I have completed most of the mechanical design and am now focusing on a PDB/switch module for power distribution and easy handling of buttons, buzzers, and LEDs.


## Mechanical Design

{% include figure image_path="assets\images\wrld\in_room_sideways_look_2.png" alt="in_room_sideways_look_2"
%}

- 9 DC Servos (Feetech STS-3215-C044) --> 2 for hip, one for knee per leg; 2 for neck; 1 for torso translation

{% include figure image_path="assets\images\wrld\translate_focused.png" alt="translate_focused"
%}

- One eye is a LED button and the other is a RasPi Cam 2

{% include figure image_path="assets\images\wrld\wrld_face_blink.gif" alt="face_blink"
%}

- Carbon Rods for legs which increase stiffness while decreasing weight

{% include figure image_path="assets\images\wrld\leg_close_up.png" alt="leg_close_up"
%}

{% include figure image_path="assets\images\wrld\back_of_head.jpg" alt="back_of_head"
%}