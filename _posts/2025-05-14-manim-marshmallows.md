---
layout: post
title: Using the Manim and Manim-Physics Library to Visualize Ice Sheet formation
date: 2025-05-14 11:45:00
description: Manim with Marshmallows
tags: python manim manim-physics science
categories: posts projects
giscus_comments: true
featured: false
---

<div style="text-align: center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/wKWT4p44UbE?si=GAPzQed_j_yiS0QS" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<div style="text-align: center;">
    <div class="caption">
    Manim Ice Sheet Visualization 1
    </div>
</div>

<div style="text-align: center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/x3oz7bBvP7c?si=vmnf-COlorWsvez2&amp;start=125" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<div style="text-align: center;">
    <div class="caption">
    Manim Ice Sheet Visualization 2
    </div>
</div>

The high school that I teach at in Japan is designated as a Super Science High School (SSH School). It’s a prestigious designation so much that only a few hundred or so schools in the entire country are SSH schools. And unlike that “California Distinguished School” Title that always adorned schools in California but never understood what that actually gave the school, being an SSH school gives a hefty sum of government grant money to support science related activities.

Where I play into this (and apparently why I was chosen to be an ALT at this school specifically) is that the SSH curriculum includes a Science English Course that I and other teachers have developed for the first time. In the course we have students read research articles in English and try to develop scientific thinking and expression with a western mindset. Research articles are too specialized and difficult for even native speakers to understand, so I relied immensely on Science Journals for Kids and Teens, a curated website of actual research articles translated into easier English accessible for kids and teens (the audience technically are kids and teens whose primary language is English). We choose papers from the major science courses conducted at the school: Chemistry, Physics, Biology, and Earth Science.

The first paper we showed students was a chemistry based paper, talking about the melting of glaciers in Greenland. In the first year of the course, we had students primarily read the Science Journal for Kids and Teens version of the paper and answer questions that I and other teachers made. Even the Kids version of the paper was difficult for Japanese High School ESL learners, so this year I used AI to simplify the paper even further while changing a few words here and there based on the vocabulary they likely knew at the first grade level. And instead of merely reading difficult English articles, my goal was to make science demonstrations that utilized more realia and different mediums of learning to understand science concepts.

I wanted a win-win demonstration. A demo that motivated me and utilized the skillsets I was already cultivating, but also relevant to the research article and engaging enough for students. I was deep into graphics programming at the time, developing visual WebGL apps in the browser using C++ and WebASM. Could I make a WebGL demo to show to students? It would have been ideal, but to make anything related to Greenland and Glaciers would be not possible but time-consuming and require many iterations.

During this time I was revisiting 3blue1brown videos and thought why not try to dabble in this library for the course? The advantage is that all the components and pieces are there, and plenty of examples if I get stuck.But now what to make? I thumbed through the paper and put myself in the shoes of a student. If I were reading this for the first time, what questions would I have? A natural question that comes up is how glaciers form, and consequently the larger ice sheet they turn into. I was able to discover some very helpful visualizations showing the melting front at the glacier, but nothing visual about the ice sheet itself.

I like to think of the ice sheet + glacier complex as a giant mass balance equation where the amount of ice that exists on Greenland at any given moment is given by: how much ice is melting and how much ice is forming. The ice that forms the ice sheet melts from the warming ocean temperatures (and apparently melts from below as explained in the paper) as well as the sun shining on top during summer. Ice is added slowly by falling snow that covers the ice sheet over thousands of years. It is a peculiar thing that a small snowflake can pile over many many layers and over centuries of time to form this massive behemoth of the Greenland ice sheet. And that these massive layers are actually moving over the years perhaps in part due to the melting that was going on.

I wanted to see if I could capture this formation in a manim visualization. My plan was to simulate snow falling over time, and use the manim-physics engine to show the snowflakes piling on top, sliding and moving like a real sheet of ice.

You will notice that I have chosen to visualize the snowflakes as square. Before showing them the visualization, I took a small bag from my pocket. It was a bag of marshmallows and I said, “Imagine that this one marshmallow is one small snowflake. What happens if I put another marshmallow (snowflake) on top? How about another? and Another? How many many of them”? Even with 20 marshmallows, the extent of the answers are “nothing happens” or “the marshmallows fall over each other and roll away”.

That’s where the manim visualization comes in. A single marshmallow, a single snowflake is insignificant. But nature loves to surprise us with the infinitesimal. I hoped that students would perceive that a small marshmallow multiplied by 100, 1000, 1000000, over many years can lead to something quite massive indeed.

## References

- <a href="https://www.sciencejournalforkids.org/articles/how-is-the-ice-in-greenland-melting/" style="color:var(--global-theme-color)">Science Journal for Kids Article</a>
- <a href="https://docs.sunfounder.com/projects/davinci-kit/en/latest/index.html
  " style="color:var(--global-theme-color)">Raspberry Pi Sunfounder Kit with the Distance Sensor and Useful Video Tutorials</a>
