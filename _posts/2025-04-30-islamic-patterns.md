---
layout: post
title: Islamic Patterns
date: 2025-04-30 09:30:00
description: A implementation in C++ and Web Assembly
tags: c++ webgl art graphics
categories: posts projects
featured: true
giscus_comments: true
---

I traveled with my family to Spain in late 2024 and I was enamored with the art and architecture. More than the Christian/Catholic motifs which emphasized tangible humans and figures of Christ I was particularly interested in the Islamic designs which were subtle, and abstract. There was a kind of mathematical elegance to them, with a simple base but extrapolated with complexity.


<div class="venobox-group" style="display: flex; justify-content: center; align-items: center; flex-wrap: wrap; gap: 15px;">
  <a class="venobox" data-gall="myGallery" href="https://lh3.googleusercontent.com/d/13NyVIUP-Qusyp72BH-fwDaJeSdUfJkGe" id="alhambra_1">
    <img src="https://lh3.googleusercontent.com/d/13NyVIUP-Qusyp72BH-fwDaJeSdUfJkGe=s300" />
  </a>

  <a class="venobox" data-gall="myGallery" href="https://lh3.googleusercontent.com/d/1SSlspWbk_AWCsYY53IefqD3stQXQ7nqa" id="alhambra_2">
    <img src="https://lh3.googleusercontent.com/d/1SSlspWbk_AWCsYY53IefqD3stQXQ7nqa=s300" />
  </a>

  <a class="venobox" data-gall="myGallery" href="https://lh3.googleusercontent.com/d/1O9wZmi0roHoAW8zyygbFcAU24upebSfD" id="alhambra_3">
    <img src="https://lh3.googleusercontent.com/d/1O9wZmi0roHoAW8zyygbFcAU24upebSfD=s300" />
  </a>
</div>


<!-- <div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <div class="embed-responsive embed-responsive-16by9 rounded z-depth-1">
            <iframe src="https://drive.google.com/file/d/13NyVIUP-Qusyp72BH-fwDaJeSdUfJkGe/preview" class="embed-responsive-item" style="border:0;" allow="autoplay"></iframe>
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <div class="embed-responsive embed-responsive-16by9 rounded z-depth-1">
            <iframe src="https://drive.google.com/file/d/1SSlspWbk_AWCsYY53IefqD3stQXQ7nqa/preview" class="embed-responsive-item" style="border:0;" allow="autoplay"></iframe>
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <div class="embed-responsive embed-responsive-16by9 rounded z-depth-1">
            <iframe src="https://drive.google.com/file/d/1O9wZmi0roHoAW8zyygbFcAU24upebSfD/preview" class="embed-responsive-item" style="border:0;" allow="autoplay"></iframe>
        </div>
    </div>
</div> -->


<div class="caption">
    Some of the Islamic Architectural Motifs I saw at the Alhambra in Granada, Spain.
</div>

I remember obsessively reading about creating these Islamic patterns on the trains to and from Toledo, when I stumbled the work of Craig Kaplan, who was doing research on algorithmically generating these patterns in code.

The Coding Train did a wonderful video tutorial on how to implement Craig Kaplan's research in Javascript. This is an implementation of their work; here I reimplemented it in C++ and WebGL/WebAssembly. It was not trivial; it was an interesting exercise to reinvent p5's line draw calls in native C++.

<div class="l-page">
  <iframe src="{{ '/assets/html/islamicpatterns_1.html' | relative_url }}" frameborder='0' scrolling='no' height="500px" width="100%" style="border: 1px dashed grey;"></iframe>
</div>
<div class="caption">
    The Islamic Patterns App. Play with the Hankin Angle and Delta using the sliders and zoom out using the scroll wheel (pinch zoom on mobile)
</div>

Using a list of 1d points, I drew a 2d dimensional rectangle that is drawn by taking a pair of points and drawing a line between them. Then I compute the normals which are rotated +/- 90 degrees from the line and translate them to edges of the line. There are 4 normals, and these 4 vectors make the 4 edges of a single rectangle. That was just to draw a single line.

The Islamic Patterns are generated using a "Hankin Algorithm" which takes a regular polygon such as a square, emanates two "Hankin vectors" from the midpoint of each edge of the polygon, and extends those hankin vectors out until they intersect with another hankin vector. This is repeated for each edge, then the entire object is tiled across in X and Y. The length of each hankin vector is calculated using the law of sines and the interior angle of a regular polygon.

Eventually I'd like to have the option to change the tiling pattern to any n-sided regular polygon, and perhaps add a neon effect by changing the fragment shader. The patterns are endless…

