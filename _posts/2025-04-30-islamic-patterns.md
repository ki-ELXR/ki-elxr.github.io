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

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/alhambra_1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/alhambra_2.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/alhambra_3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
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

## 日本語

イスラミックパターンは「ハンキンアルゴリズム」を使って作られます。このアルゴリズムでは、正方形のような正多角形の各辺の中点から2本の「ハンキンベクトル」を伸ばし、それらが他のハンキンベクトルと交わるまで延長します。これを全ての辺で繰り返し、最後に全体をグリッド状に繰り返します。ハンキンベクトルの長さは、正弦法則と正多角形の内角を使って計算されます。。。。。。
