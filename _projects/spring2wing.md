---
layout: single
title: "spring2wing"
excerpt: "Jumping robot with wings (doesn't fly yet)"
date: 2025-04-27
collection: projects
header:
    teaser: assets/images/spring2wing/spring2wing_low_shot_cropped.gif
order: 2
---

---
# Inspiration

Dr. Hawke's lab at UCSB created a robot similar to this that could jump absurdly high (~100 ft).

See this [UCSB video](https://www.youtube.com/watch?v=Z1BQLSkqrpY) or the [veritasium video](https://www.youtube.com/watch?v=daaDuC1kbds).

# Our Project
---

<div style="max-width: 360px; margin: auto;">
  <div style="position: relative; padding-bottom: 177.78%; height: 0; overflow: hidden;">
    <iframe
      src="https://www.youtube.com/embed/s2asxXa2fdQ"
      title="Jump"
      style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
      frameborder=""
      allow="accelerometer; autoplay; encrypted-media; picture-in-picture"
      allowfullscreen>
    </iframe>
  </div>
</div>

---

This project was for ME-423 which is 'Robotics: Fundamentals and Applications'. The original scope was to build a jumping robot capable of jumping and flying some somewhere. This turned out to be far too much for the limited amount of time we actually spent on the robot. Getting all the electronics and jumping mechanics to work took much longer than expected so the flying became more of an aesthetic accessory.

{% include figure image_path="assets/images/spring2wing/compressed_shot.jpg" alt="compressed_shot" 
%}

Another key aspect of our scope was to make it able to jump multiple times in a row. We were somewhat successful in this. We need a current sensor or a limit switch and this would work. Currently, I have to adjust the compression setpoint with some battery finesse, but no other action is required to do the process repeatedly.

{% include figure image_path="assets/images/spring2wing/side_shot.jpg" alt="side_shot" 
%}

# Jumping Design
---

Our design features a dc motor to compress the motor with a cable. Once the robot compresses completely, a servo actuates a lever that locks the robot in place, then our dc motor unwinds the cable. Finally, the robot pulls back the lever, launching the robot. We are using carbon fiber bars as our springs.


# CAD
---

Everything was designed in fusion 360, mostly by Kai De La Cruz.

### Isometric
{% include figure image_path="assets/images/spring2wing/isometric_cad.png" alt="isometric_cad"
%}

### Locking Mechanism
{% include figure image_path="assets/images/spring2wing/locking_mech.png" alt="locking_mech"
%}

# Electronics
---

Originally, we had come up with an assortment of components that would allow us to create a small design without a pcb. In theory it should have worked, but some problems with the microcontroller, battery life, and project deadline forced us to go to a less ideal design.

### Original Circuit Setup
{% include figure image_path="assets/images/spring2wing/original_circuit.jpg" alt="original_circuit"
%}

We ended up with an Arduino Nano and a 9V battery which increased our weight, but allowed us to jump.

# Testing
---

Like all good final projects, we finished the circuit, the progamming, the mechanical design and tested in the day before it was due. Comically, we came up with the locking mechanism that day and swapped from a SEEED ESP32 to a ESP32 Devkit to an Arduino Nano. About 14 hours of fiddling and we got our first succesful jump.

<div style="max-width: 360px; margin: auto;">
  <div style="position: relative; padding-bottom: 177.78%; height: 0; overflow: hidden;">
    <iframe
      src="https://www.youtube.com/embed/yehSviDhSpo"
      title="First Successful Test"
      style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
      frameborder="0"
      allow="accelerometer; autoplay; encrypted-media; picture-in-picture"
      allowfullscreen>
    </iframe>
  </div>
</div>

### Take Off View

<div style="max-width: 360px; margin: auto;">
  <div style="position: relative; padding-bottom: 177.78%; height: 0; overflow: hidden;">
    <iframe
      src="https://www.youtube.com/embed/ejHEGNCBb9o"
      title="Bottom View"
      style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
      frameborder="0"
      allow="accelerometer; autoplay; encrypted-media; picture-in-picture"
      allowfullscreen>
    </iframe>
  </div>
</div>