---
layout: post
title: Measuring the Speed of Sound in Air and Water Using a Raspberry PI and a HRSR04 Ultrasonic Distance Sensor
date: 2025-06-11 11:45:00
description: Is sound faster in air or water?
tags: python raspberrypi sound manim manim-physics science
categories: posts projects
giscus_comments: true
featured: false
---

<div style="text-align: center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/E0yz5klLzbY?si=z2zOk83lB-c1mP5k" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<div style="text-align: center;">
    <div class="caption">
    Measuring the distance / speed of sound in air.
    </div>
</div>

<div style="text-align: center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/QXFgizeic0c?si=kRqsHRFyERuEN-92" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<div style="text-align: center;">
    <div class="caption">
    Measuring the distance / speed of sound in water.
    </div>
</div>

In the previous blog post, I mentioned how I wanted to utilize different ways of learning for the Science English course

Usually for any paper that I show to students, I like to get my own hands dirty and understand the research. That often involves my own investigations and discovery process about the topic. One of the things that was curious to me was how exactly scientists managed to map the glaciers all across Greenland. Surely they needed some long distance device to map out the topography. From what I’ve read, it seems like they use satellites to map the surface of the water (and hence the sea level), and use sonar equipped on sea-faring vessels to map the underwater surface of the glaciers.

At the school, along with the Science English course, there are Science Research Method and Science Research Process courses that go over the methodology and design of the scientific method. It’s quite amazing, I wouldn’t be lying if I wasn’t a bit jealous that the students are able to have this experience at the high school level. As part of developing their own experiments and research, each group of students has a Raspberry Pi Kit and DaVinci Sunfounder Kit with various sensors and IC chips. Well there wasn’t a mini-satellite included with the kit, but there was an ultrasonic distance sensor which operated with the same underlying principles as sonar. Bingo.

While I was searching up the speed of sound, I realized that the speed of sound was several times faster in water than in air. My first gut instinct was that sound in air was faster because molecules have to have higher kinetic energy to vaporize into the gas phase. But the reality is that the compressibility and density of the water make it easier for the energy to transmit through it.

Before the demonstration, I asked students whether they believed sound was faster in air or water. Then I placed the empty beaker underneath the distance center and printed the distance and time the sound traveled to the console in real time. After we were able to confirm the general values, I took the beaker while the code was still running and filled it with water with the sink nearby. Then I placed it again underneath the sensor and was able to confirm that yes, the sound traveled faster in water. It was fun putting the demonstration together and I was happy that I was able to demonstrate the principle without needing a lot of fancy equipment (or water!)

## References

- <a href="https://www.sciencejournalforkids.org/articles/how-is-the-ice-in-greenland-melting/" style="color:var(--global-theme-color)">Science Journal for Kids Article</a>
- <a href="https://docs.sunfounder.com/projects/davinci-kit/en/latest/index.html
  " style="color:var(--global-theme-color)">Raspberry Pi Sunfounder Kit with the Distance Sensor and Useful Video Tutorials</a>
