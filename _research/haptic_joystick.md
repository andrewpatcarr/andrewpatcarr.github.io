---
layout: single
title: "4D Haptic Joystick"
excerpt: "Research and design of a 4 DoF Haptic Joystick under Dr. Xiaoli Zhang"
date: 2025-6-21
collection: projects
header:
    teaser: /assets/images/haptic_joystick/top_view.jpeg
order: 2
gallery:
  - url: assets/images/haptic_joystick/sw_assembly.jpg
    image_path: assets/images/haptic_joystick/sw_assembly.jpg
    alt: "assembly"
  - url: assets/images/haptic_joystick/transmission_setup.jpeg
    image_path: assets/images/haptic_joystick/transmission_setup.jpeg
    alt: "transmission"
  - url: assets/images/zap_em_blast_em/final_product.jpg
    image_path: assets/images/zap_em_blast_em/final_product.jpg
    alt: "final product"
    title: "At Demo"
  - url: assets/images/zap_em_blast_em/mosfet_swap.jpg
    image_path: assets/images/zap_em_blast_em/mosfet_swap.jpg
    alt: "mosfet_swap"
  - url: assets/images/zap_em_blast_em/LaserCaution.jpg
    image_path: assets/images/zap_em_blast_em/LaserCaution.jpg
    alt: "laser caution"
    title: "Customs" 
  - url: assets/images/zap_em_blast_em/mountedPCB.jpg
    image_path: assets/images/zap_em_blast_em/mountedPCB.jpg
    alt: "pcb exploded"

transmission:
  - image_path: assets/images/haptic_joystick/transmission_setup.jpeg
    alt: "transmission"
    title: "Transmission"
    excerpt: "- Travel: 22° Θ and 36° ɸ 
    

            - With motor shaft flange adapter, bearing mounts, motor mounts"
joystick:
  - image_path: assets/images/haptic_joystick/joystick_top.jpeg
    alt: "Joystick"
    title: "Joystick"
    excerpt: "- syringe plunger stabilized with metal rods
            
              - allows easy wire organization through the joystick
            
              - integrates vibration motor in a minimal but effective way

              - houses syringe"

---

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/haptic_joystick/top_view.jpeg" alt="top_view"
%}
</div>

As part of the Colorado School of MINES FIRE program, I designed and prototyped a 4D haptic joystick working under Dr. Xiaoli Zhang in collaboration with PhD student Grant Zheng.

The mechanical design is based on other haptic joysticks on the market and previous research completed. Two geared DC motors with encoders control Θ and ɸ, and a servo powers a hydraulic syringe system to actuate in the z direction along the joystick. Vibration motors in the joystick top provide options to show spin, give positional guidance, or add to impact simulation. The DC motors can output roughly 4 N-m of torque each. 

A Raspberry Pi 3 B+ is used to do computations and send out commands. Since there is a data processing aspect to this project, a Raspberry Pi allows for fast processing, signal outputs, and ease of use. The device is programmed in Python utilizing an object-oriented organization. There are two high-frequency motor drivers for the DC motors, a makeshift transistor diode PWM motor driver for the vibration motor, two current sensors for calibration, and a buck converter for power distribution.

We were designing towards simulating a tennis match with the joystick top being the ball. So a user would be holding onto the ball during the match as it went back and forth across the court. They would feel the impacts and kinematics the ball undergoes during the match. 
We were able to achieve a successful simulation of the match with x-y data. There is a machine-learning part of this project that I am not a part of that is still working on getting the z-data of a given tennis match video. 

Work is still being done to optimize the design and complete user studies.

# Design Overview

### Mechanical Design

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/haptic_joystick/sw_assembly.jpg" alt="assembly"
%}
</div>

---

{% include feature_row id="transmission" type="left" %}

{% include feature_row id="joystick" type="left" %}

### Electronics

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/haptic_joystick/electronics.jpeg" alt="electronics"
caption = "Raspberry PI 3 B+, high power H-bridges, power sensors, transistor circuit for vibration motors, buck converters. (ignore the AC current sensors, oops)"%}
</div>

---

### Control

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/haptic_joystick/control_scheme.png" alt="control"
%}
</div>

---

### Simulation Technique

To simulate the ball-racket impact, we tell the y-axis motor to go to an impossible positive angle and then an impossible negative angle, or vice versa depending on the path of the ball. This jolts the joystick in the direction of the ball's path then pulls it back rapidly before starting its next trajectory. This results in forces that the user can feel and relate to what they are seeing on the screen. 

---

## Path Following Results

***A full simulation***
<div style="width: 500px; margin: auto;">
{% include figure image_path="assets/images/haptic_joystick/results.png" alt="results"
%}
</div>
***Haptic Impact***
<div style="width: 500px; margin: auto;">
{% include figure image_path="assets/images/haptic_joystick/results_closeup.png" alt="results"%}
</div>

---

**Work continues at MINES**