---
layout: post
title: Digitized Dance
date: 2025-12-09 09:30:00
description: Mediapipe JS, Openframeworks, and Emscripten
tags: c++ webgl dance art graphics openframeworks mediapipe computervision
categories: posts projects
giscus_comments: true
featured: true
---

This project was born out partly out of my frustrations with Python and OpenCV. In a nutshell, OpenCV is made for image processing, not for live video processing so it is really difficult to perform computer vision on a live webcam and saving the video with the correct framerate.

Doing this I also realized how much of a mess MediaPipe is under the hood and how it is much, much easier interfacing with the Python or Javascript APIs instead of rebuilding it from source in C++.

This works on desktop or mobile. Allow the website access to your camera and stand far enough away for Mediapipe to detect your whole body! The recording feature only works on desktop as of right now.

<div class="l-page">
    <iframe 
    src="{{ '/assets/html/mediapipe-js_1.html' | relative_url }}"
    frameborder="0"
    scrolling="yes"
    width="100%"
    style="border:1px dashed grey; height:90s0vh; min-height:800px;"
    ></iframe>
</div>
<div class="caption">
    
</div>

## References

- <a href="https://github.com/ki-ELXR/python-bodydetection-mediapipeshader" style="color:var(--global-theme-color)">Link to Repo</a>
