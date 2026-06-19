---
layout: post
title: Sound Waves Visualized with Manim
date: 2025-06-11 11:45:00
description: A traveling wave is harder to program than it looks
tags: python sound manim science
categories: posts projects
giscus_comments: true
featured: false
---

<div style="text-align: center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/kLIU35PC9Fw?si=Pfx6LwgUz5Qhb5KB" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<div style="text-align: center;">
    <div class="caption">
    A visualization I made using manim to show how sound can be modeled as a longitudinal wave.
    </div>
</div>

In trying to understand why sound in air is slower than sound in water, I really needed to get to the physics behind the question. While many people are concerned about misinformation and content bloat in today’s internet, there are rich sources of information out there if you are willing to have a persistent but critical eye.

One such source is "Sound: An Interactive eBook" by Kyle Forinash and Wolfgang Christian. They have got a comprehensive set of simulations about sound waves and wave theory in general. Sound is a pressure wave that travels through a medium and can be modeled as a longitudinal sine wave. Their simulations are straightforward and easy to understand, but I wanted to see if I could stretch my manim muscles and make my own visualization.

Ever since 3blue1brown released his manim animation engine to the public, a whole movement of 3b1b-esque creators have risen and made youtube videos about a whole list of other scientific topics other than math. And there is a thriving Discord server where fellow manim users can share and troubleshoot their creations. All the resources out there have been essential for getting my feet wet into the manim engine, but unfortunately, no one had ever really made their own longitudinal wave animation and shared it publicly.

Putting all the pieces together was a multitude of rabbit holes like trying find similar 3b1b videos that showed sinusoidal motion (his light tube videos had what I was looking for but way too complicated for me to try to implement in the manim community edition), or trying to hack the simulations themselves to get any idea of the animation involved (unfortunately a lot of these simulations were old java applets that I didn’t know how to decompile from the browser).

I knew the math behind the motion, could visualize it in my head, but couldn’t get the computer to do the same thing.

Getting the wave to oscillate cleanly in the window size was tricky business, and often required some aesthetic tuning (read: brute force trial and error) to get to something visually appealing. I was able to find some decent parameters off of a Mathematica simulation…after going down another rabbit hole trying to get Python to run Mathematica files.

<!-- The other key piece here was getting the manim animation to play as I liked -->
<!-- ChatGPT to the rescue. Apparently the variable is not stored and allows each particle along the wave to move independently and ChatGPT suggested that …. -->

I would literally not have been able to make my manim animation without studying how the other guys made their visualizations, and I am grateful they made it open source for anyone to be able to learn and be inspired from. On the other hand, there is a small part of me that looks at these animations and doesn’t like the “education aesthetic” of their design. It feels like some of these were made during the early Internet / flash days (and honestly a high chance that they actually were) and lacks some visual polish. Don’t get me wrong, the substance is there and they don’t miss on educational understanding. Which really is the more important of the two if I had to give up one.

I suppose it is more a compliment to 3blue1brown’s work and how he is able to have both the educational depth but an elegant aesthetic. It is kind of like a film where you can usually watch one with ok cinematography but a strong script but can’t resonate with a film with a bland script but Michael Bay visuals. Both are needed, I think, to deliver a powerful message. And when the two play nicely, wow. That message has a different sort of vibe.

## References

- <a href="https://www.compadre.org/books/?ID=46&FID=45042" style="color:var(--global-theme-color)">Sound: An Interactive E-book</a>
- <a href="https://www.physicsclassroom.com/Physics-Interactives/Waves-and-Sound/Simple-Wave-Simulator/Simple-Wave-Simulator-Interactive" style="color:var(--global-theme-color)">An Interactive Simple Wave Simulator</a>
- <a href="https://www.sciencejournalforkids.org/articles/will-artificial-trees-be-the-next-power-plants/" style="color:var(--global-theme-color)">Science Journals for Kids Article</a>
- <a href="https://phys.libretexts.org/Bookshelves/University_Physics/University_Physics_(OpenStax)/Book%3A_University_Physics_I_-_Mechanics_Sound_Oscillations_and_Waves_(OpenStax)/17%3A_Sound/17.03%3A_Speed_of_Sound" style="color:var(--global-theme-color)">Speed of Sound Equation and Speeds for Various Media</a>

https://www.sciencejournalforkids.org/

https://www.sciencejournalforkids.org/articles/how-is-the-ice-in-greenland-melting/

https://docs.sunfounder.com/projects/davinci-kit/en/latest/index.html
