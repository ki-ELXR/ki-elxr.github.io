---
layout: post
title: Making Wind Energy Using a DC Motor, a Raspberry Pi, and an ADC0834
date: 2025-07-09 11:45:00
description: A DIY project to demonstrate the power of air.
tags: python raspberrypi science matplotlib ADC0834
categories: posts projects
giscus_comments: true
featured: false
---

<div style="text-align: center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/KjV7sbc0DSQ?si=_PHKofa6O4bOCkZ_" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<div style="text-align: center;">
    <div class="caption">
    Demonstration of the Wind Turbine
    </div>
</div>

From my laptop I use RealVNC Viewer to remote into the Raspberry Pi. The python script is run from the terminal which loads the ADC0834 library and begins to display the values in the terminal window. Until ctrl+c is pressed, the values continue to print to the window and the matplotlib plot continues to be updated with the values.

In the plot, I have labeled the Y-axis as voltage, but this is technically not the correct unit.
The ADC output is a digital, dimensionless output and the range is determined by the chip itself (for this chip the range is from 0 - 255). I’d imagine you could convert this into real values or a real voltage using some sort of calibration, but I didn’t need this level of thoroughness for a proof of concept demo.

<div style="text-align: center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/2rbaYqhp0MM?si=aPa-04OG8xgmjS05" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<div style="text-align: center;">
    <div class="caption">
    Screen capture of the Raspberry Pi terminal during the demonstration
    </div>
</div>

The second article that students have to read in English is “Will artificial trees be the next power plants?”, based on a 2017 research article from Iowa State University. In the paper, scientists used piezoelectric strips in the shape of cottonwood leaves to generate electricity.

I was thinking about a classroom demonstration that could best embody the theme of the paper while also utilizing the materials I had at school. Since I was planning on talking about wind energy in general, I introduced wind turbines and how they work. DaVinci Sunfounder Kit comes with a DC motor and fan attachment that you can power with a battery. In normal operation, electric charge drives the motor and causes the motor shaft to spin…surely the opposite could be possible? It was worth trying it out myself.

The DIY turbine uses a motor connected to the breadboard using an alligator clip to breadboard pin wire (I did not have any soldering equipment on hand!). As the shaft of the turbine spins, some voltage is generated and the analog value is read by the ADC0834 chip. The digital output of the ADC is fed into the GPIO pins of the Raspberry PI, and the resulting output is plotted using matplotlib.

The ADC0834 itself comes with the DaVinci Sunfounder Kit for Raspberry PI and had great tutorials to get me started with a basic circuit. The website also has premade libraries for the ADC0834 that I used and adjusted slightly for this project.

In my experience, standard DC motors that come with Raspberry PI Kits don’t have enough signal to register with the ADC0834, at least not cleanly. You are able to measure the electricity using a multimeter directly, but I wanted to display the electricity produced on a computer screen and that required a stronger signal.

The RF-330TK-07800 that I found on Rakuten and made in China has more coils than the standard hobby DC motor and so will generate more electricity per revolution. It is nowhere enough to power any sort of electric device, but it was perfect to demonstrate the concept of an electric generator. For this particular motor, there also appears to be a single rotation that generates electricity vs not.

A cylindrical shaft made of styrofoam was adhered to the motor shaft using a hot glue gun. The blades of the turbine use coffee filters with wooden skewers hot glued to the edges. The skewers puncture into the styrofoam shaft and glued accordingly.

Original prototypes of the blades used cardboard for the propellers, but it was difficult to make the shape identical between blades so the weight balance was even. The blade also needed to be curved slightly to catch the wind (real turbines have this feature as well). By using the coffee filters, I was able to have a lightweight material that could catch the wind because it was both flexible and could catch some of the wind in the interior of the coffee filter like a parachute.

My original plan was to show this to the students and have them build their own wind turbines out of cardboard, tape, and styrofoam, and have a competition to see who could make the most electricity. Unfortunately, there wasn’t enough time and the school wanted more traditional writing / reading activities, so we settled for just a single demonstration to the class. At the end of the day, getting them interested in science is meaningful enough, and hopefully this single demo sparks their interest enough to learn more on their own (pun intended).

## References

- <a href="https://www.sciencejournalforkids.org/articles/will-artificial-trees-be-the-next-power-plants/" style="color:var(--global-theme-color)">Science Journals for Kids Article</a>
- <a href="https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0170022#ack" style="color:var(--global-theme-color)">Original Article</a>
- <a href="https://pvbuzz.com/money-doesnt-grow-on-trees/" style="color:var(--global-theme-color)">Interview with the scientists behind the study</a>
- <a href="https://item.rakuten.co.jp/denshi/53366/" style="color:var(--global-theme-color)">DC Motor that generates more electricity per revolution</a>
