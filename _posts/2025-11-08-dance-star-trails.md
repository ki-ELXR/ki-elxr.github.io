---
layout: post
title: Dance Star Trails (With Python, OpenCV, OpenGL, and Mediapipe)
date: 2025-11-08 18:30:00
description: An artistic computer vision project
tags: python webgl art graphics dance mediapipe computervision
categories: posts projects
giscus_comments: true
featured: true
---

<div style="text-align: center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/GmAN9D0HsOw?si=sV1jWe8zTLMIC5ny" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<div style="text-align: center;">
    <div class="caption">
    Demonstration of the Dance Star Trails
    </div>
</div>

The Coding Train is one my favorite Creative Coders to watch. Along with opening me to the world of computer vision, he showcases some pretty cool artists making art with code.

One such artist that caught my eye was Maya Man's art pieces with PoseNet, where she combined her coding skill with her love of music and dance. Being a dancer myself, I wanted to make something similar. But I didn't know Javascript, and I am too stubborn to switch from Python and C++ (It's on the docit eventually along with Typescript).

So what better way than to rebuild it myself from the ground up using Python! (In retrospect, it was probably much simpler to just learn Javascript than to deal with all the issues I had to deal with frame rates, alpha blending with opengl and the webcam, etc. etc. etc. But it was still worth it.)

## References

- <a href="https://github.com/ki-ELXR/raspi-kaleidoscope/tree/bodypose_dance" style="color:var(--global-theme-color)">Link to Repo</a>
- <a href="https://googlecreativelab.github.io/posenet-sketchbook/" style="color:var(--global-theme-color)">Maya Man's PoseNet Dance Artwork</a>
- <a href="https://www.youtube.com/watch?v=vfNHdVbE-l4" style="color:var(--global-theme-color)">The Coding Train's Hand Pose Detection with ml5.js Tutorial</a>
