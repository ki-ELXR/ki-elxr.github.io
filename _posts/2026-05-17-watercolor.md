---
layout: post
title: Watercolor emulations
date: 2026-05-17 09:30:00
description: Implementing KYND's watercolor emulation in openframeworks.
tags: c++ webgl art graphics openframeowkrs
categories: posts projects
featured: true
giscus_comments: true
---

I 

### Example of Sub-Heading 1






<div class="caption">
    Some of the Islamic Architectural Motifs I saw at the Alhambra in Granada, Spain.
</div>

I remember obsessively reading about creating these Islamic patterns on the trains to and from Toledo, when I stumbled the work of Craig Kaplan, who was doing research on algorithmically generating these patterns in code.

The Coding Train did a wonderful video tutorial on how to implement Craig Kaplan's research in Javascript. This is an implementation of their work; here I reimplemented it in C++ and WebGL/WebAssembly. It was not trivial; it was an interesting exercise to reinvent p5's line draw calls in native C++.

<div class="l-page">
  <iframe src="{{ '/assets/em/em-shaderexample/index.html' | relative_url }}" frameborder='0' scrolling='no' height="500px" width="100%" style="border: 1px dashed grey;"></iframe>
</div>
<div class="caption">
    Watercolor Emulation
</div>

Ending

## References

- <a href="https://kyndinfo.notion.site/Pencils-Brushes-and-Paints-54c0f94aa30940aba2f11b637dc009c2" style="color:var(--global-theme-color)">KYND's emulation of watercolor, pencils, and brushes in p5.js</a>