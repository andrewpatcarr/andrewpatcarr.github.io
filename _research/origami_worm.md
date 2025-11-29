---
layout: single
title: "2-DoF Origami Worm"
excerpt: "Research and design of a 2 DoF origami worm robot under Dr. Mohammad Hasan"
date: 2025-04-25
collection: projects
header:
    teaser: /assets/images/origami_worm/origami_worm.gif
order: 2
toc: true
toc_label: "Table of Contents"
toc_sticky: false
---

<div class="video-container">
  <iframe width="560" height="315"
    src="https://www.youtube.com/embed/ye4EfqBf8xg"
    title="worm worming"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen>
  </iframe>
</div>

## Overview 

This project started as a Cal Poly SURP in 2023. I joined in the beginning of 2024. I worked under Dr. Mohammed Hasan with undergraduate students Micheal Freeman, Conor Schott, Carter Josef, and Col Cook. 

Most of my work was on getting the robot to move well. The origami pattern was already created and worked well. We needed to program it for cyclic motion and keyboard inputs. I worked to characterize the stiffness of different origami springs and generalize it to certain metrics of the springs. 

There were many developments in the material of the origami, the design of the friction pads, the material of the string, and the method of control. 

We published a paper at the 2024 ASME IDETC-CIE where Michael and Conor presented our work. 

The paper can be found the [ASME Website](https://asmedigitalcollection.asme.org/IDETC-CIE/proceedings-abstract/IDETC-CIE2024/88414/1208996).

Following this, I continued work on the origami worm. Because of the
properties of origami structures, origami robotics are often hard to reproduce. Our robot struggled with this: the motion was inconsistent, and it was difficult to test new worm angles and friction pads. As part of ME-400 (Special Problems for Advanced Undergraduates), I redesigned the robot.
I redesigned all the motor mounts, developed a clamping system to attach the origami spring, created a fast-mounting system for 3D-printed directional friction pads, and swapped from servos to DC motors
controlled by an analog joystick.

Currently, we are still working on consistent forward motion. This includes designing new 3D printable ideas, trying new materials like PDMS and trying electromagnets.

## Chronological Details:

### Design

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/worm_diagram.jpg" alt="worm_diagram"
%}
</div>

The robot consists of two servo motors that sit on opposite sides of the robot. They have a tendon that connects directly to the other side that is off-center. This allows the robot to compress and decompress in unique ways which can illicit forward motion and turning motion. The friction pad on the bottom of each support makes the forward motion possible. 

### Stiffness Testing

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/stiffness_testing_setup.jpg" alt="stiffness_testing_setup"
%}
</div>

To characterize and generalize the stiffness of the Rigiccordion spring, we completed stiffness tests using a mill and commercial scale. This allowed us to show the linearity of the spring's stiffness. We also developed empirical correlations to try to predict the stiffness of different size Rigiccordions. These correlated relatively well using the perimeter of the spring, the number of folds, and the radius of each fold along with a material factor. 

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/equations_diagram.png" alt="equations_diagram" caption="Stiffness modeling equations and their definitions"
%}
</div>

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/stiffness_table.png" alt="equations_diagram" caption="**Ks** is the material stiffness coefficient. For Inkjet paper, Ks was 0.112 oz-in with a standard deviation of 0.0167 oz-in."
%}
</div>

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/mylar_curve.jpg" alt="equations_diagram" caption="Stiffness curve for a Rigiccordion made of Mylar" width="300"
%}
</div>

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/paper_curve.jpg" alt="equations_diagram" caption="Stiffness curve for Inkjet paper Rigiccordion springs" width="300"
%}
</div>

### Directional Friction Pads

After weeks of watching the robot sliding randomly, we came up with the idea
of directional friction pads. These were to slide in one direction and hold in the other which would let the rear support come forward as the front support stayed still and vice versa.

Our first success used folded paper pads, as seen in the video at the top. These worked well but slowly disintegrated, and only worked on very specific surfaces. However, this success gave us hope that smooth and consistent motion was possible without the use of any rotary mechanisms for traction. 

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/paper_friction.jpeg" alt="paper_friction" 
%}
</div>


## Robot Redesign

Previously, the origami spring was attached with tape to the supports. During testing, the spring would slip and was difficult to detach and reattach. A new mechanism was designed to allow quick on/off and one that would hold the spring in place well.


### Clamping System

The new system has a clamp that sandwiches the spring between two plastic pieces. The clamp has edges that when fully put together will add extra resistance to coming apart.

<div style="width: 500px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/paper_test.jpg" alt="paper test" caption="Paper Fit Test"
%}
</div>

<div style="width: 500px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/cross_section.png" alt="Cross-section" caption="Cross-section of Clamp System"
%}
</div>

### Friction Pad Fast-mounting System

Since the new spring attachment system had an outer shell, this opened up the opportunity to add a way to attach friction pads directly. On the old system, friction pads were taped on. The new system used rails on the friction pads that would slide into a slot on the outer shell of the clamp. The rails are 1.3 mm thick, and the slot is 1.5 mm thick.

<div style="width: 500px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/friction_pad_rails.png" alt="rails" caption="Friction Pad with Rails"
%}
</div>

<div style="width: 500px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/clamp_system.png" alt="clamp system" caption="Clamp system with fast-mountain friction pad system"
%}
</div>

### Servos to DC Motors

The original design used continuous rotation servos for actuation. These were quick to implement, cheap, and in the lab. The servos were small and weak so they sometimes could not compress the asymetrical spring at the same rate. Also, they had a small plastic shaft with a star design. This made it very difficult to 3D print new parts that would couple securely.

The right DC motor could solve all the problems with the servos. We needed a DC motor with an encoder that was strong enough to compress the robot completely. A quick calculation was done to estimate the maximum torque necessary to hold the robot in full compression and to compress the robot at a rate similar to the previous robot. Stiffness data was used from the previous paper.

A Pololu micro-geared DC motor was selected. An option with a 298:1 gear ratio fulfilled both the torque and speed. This motor was also very small and had an encoder built-in.

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/motor_mount.jpg" alt="motor mount" caption="New Motor Mount Design"
%}
</div>

Since new motors were used, the motor mounts needed to be redesigned. The mounts were designed to be in line with the other side's connection and were to be as minimal as possible. Also, the mount features a spot for a screw to be screwed in to hold the other side of the tether. There were many different spots where the tether could be attached.

### Pulleys

Pulleys were designed to fit on the motor shafts and needed to be able to attach the tether well. The pulleys press fit tightly onto the shaft. There is a hole for a screw to lock onto the shaft but the plastic threads do not hold well enough to do anything. The pulley has a hole to tie the tether into.

<div style="width: 500px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/pulley.png" alt="pulley"
%}
</div>

### Friction Pad Design

Friction pads were designed that could be 3D printed to achieve directional friction. These were printed out of TPU. The designs all revolved around a sawtooth with differing lengths, thicknesses, and angles. This is still undergoing work to characterize what aspects of the pads affect motion, increase performance, and allow forward locomotion. 

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/friction_pad_designs.png" alt="friction pad designs"
%}
</div>

### User Input

Previously, the robot was controlled by a timed sequence. This was easy to implement but without any speed control, the motors would get out of sync and it was hard to realign them. A way to control the robot live would make the testing and movement much easier.

An analog joystick was used for user input. A plastic joystick was fit to the small metal joystick piece, and a housing was made to hold the joystick and Arduino side by side.

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/joystick_arduino_setup.jpg" alt="joystick_arduino" caption="Joystick and Arduino Setup"
%}
</div>

Pushing the joystick forward compresses both motors and vice versa. Pushing it to one side rotates a given motor depending on if its forwards or backwards.

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/joystick_decoding.jpeg" alt="joystick_decoding"
%}
</div>

### Controller

A speed-based PI controller was used to go to a specific speed based on how forward the joystick was. If the motors become off, the system corrects this until the motor's angles are realigned.

<div style="width: 700px; margin: auto;">
{% include figure image_path="assets/images/origami_worm/controller_scheme.jpg" alt="controller scheme"
%}
</div>

### Movement Results

Once the new robot was fully working, tests could be completed using different friction pads and worm angles. This is still undergoing work. Movement is very dependent on the ground surface: roughness and angle. With all the different variables that affect the motion, it is very difficult to understand what is doing what. Sometimes the robot will work as planned, sometimes won't work at all, and sometimes will do the opposite of what is expected. 

We are currently playing around with the worm angle by adjusting the tether connection point which changes the balance of moments about the center of action. This changes how the robot puts pressure into the pads. We are also trying an assortment of friction pad designs and where the pads sit relative to the mounts. Since they are friction fit into the mounts, they can be moved in and out of the mount to move the feet more or less outward.
