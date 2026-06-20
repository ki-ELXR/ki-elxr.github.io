---
layout: post
title: Measuring UV Light with the ML8511 UV Sensor, ADC0834, and a Raspberry Pi
date: 2025-11-11 11:45:00
description: A DIY project to detect the presence of UV Light.
tags: python raspberrypi science matplotlib ML8511 ADC0834
categories: posts projects
giscus_comments: true
featured: false
---

<div style="text-align: center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/g4mvvlr9HLQ?si=hkeRjsaVYwIMzXQK" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<div style="text-align: center;">
    <div class="caption">
    Demonstration of the ML855 UV Sensor
    </div>
</div>

One of the 2nd year students undergoing biology research asked me a favor. "Can you help us with our Raspberry Pi?" Their keyboard and mouse weren’t working. I walked with them to the lab and troubleshooted the problem. Many years back, when I was first working with lasers as a process engineer, my coworker and I had issues trying to get the laser to operate. We tried a myriad of things and ended up staying until 11PM with no resolution in sight. As a last resort, we called one of the senior laser engineers while he was at home and asked him for advice. “Did you try turning off the computer and turning it back on?”. It was so stupidly simple and yet it was the thing that worked. Since I never forgot the power of the simple and the obvious.

So a simple reset of the Raspberry Pi fixed their Keyboard and Mouse problem, but it seemed they were having trouble getting their circuit working. They were growing tomato plants and used a UV blocking sheet over them. They ordered a ML8511 UV Sensor and wanted to measure if the UV was being blocked through the sheets.

I asked them if they needed help, but not before asking if they really, really needed it. It’s easy to demand the stars when you’re not on the hook for delivering results. I proposed I would make the circuit for them if they documented how to build and use it for future students. They agreed.

I was personally excited at the mini-project. They were trying to use an analog UV sensor to interface directly with the Raspberry Pi based on the tutorial they found, but that tutorial used an Arduino/Raspberry Pi Pico, which both have onboard analog-to-digital converters. The regular Raspberry Pi doesn’t have that so you need a separate chip to do the conversion. It was lucky that their kit already had the ADC0834, and even luckier that I had already built a circuit that used it - making a wind energy generator (see the other blog post).

After a weekend afternoon or so of troubleshooting, I wasn’t able to get any reading (the output value was just 128, which is half the max analog value that gets read). Turns out the problem was the connection - the ML8511 was sitting on header pins that are plugged into the breadboard, and those pins needed to be soldered. Another piece of luck - I asked around and one of the chemistry teachers had a soldering kit at the school. I bought the kit home, watched some Youtube Videos to refresh memory (I had only soldered once, back in my very first job), and did it after school that same day.

<div class="row">
    <a class="venobox" data-gall="myGallery" href="https://lh3.googleusercontent.com/d/1fDtJtHpk79KOf20WPBAEvAUdICHG-Fu5" id="ML8511_UVSensor_Solder_2">
        <img src="https://lh3.googleusercontent.com/d/1fDtJtHpk79KOf20WPBAEvAUdICHG-Fu5=s300" />
    </a>
</div>
<div class="caption">
    My amateur job at soldering the ML8511 to header pins
</div>

And the last piece of luck - one of the biology teachers had a UV fluorescent lamp sitting around in storage that was perfect for testing. Worked like a charm! I even connected it to a battery pack and bought it outside on a cloudy day and it also registered the sunlight.

A few things of note: the value of the ADC0834 is 8 bits so it can output a value anywhere from 0 - 256 (2^8). There are no units and the values need to be converted to a real measurement based on your sensor. There are some rough linear equations to convert that to a UV - Index. I didn’t get a lot of range in the response, and I’m not sure it is because it was connected directly to the ADC0834. The spec sheet recommends connecting it with a load resistor and OpAmp. The last thing I will say is be careful of which header pins you solder. The header pins that came with the sensor fit into the breadboard but are too small to connect to the jumper wires. Having the jumper wires is ideal so you can move the ML8511 around as the angle of incidence changes the value of the sensor.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/UVSensorML8511_ADC0834.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Circuit Diagram for the UV Sensor
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ML8511_UVSensor_CircuitActual_1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ML8511_UVSensor_CircuitActual_2.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>    
</div>
<div class="caption">
    Actual Completed Circuit of the UV Sensor
</div>

I’m not sure if most high school students can do this on their own. I’m sure there are precocious students out there who have done this kind of thing, but this would have felt impossible to the me in high school. Learned a hell of a lot since then.

## References

- <a href="https://github.com/ki-ELXR/raspi-adc0834-sensing" style="color:var(--global-theme-color)">Link to Python Files</a>
- <a href="https://cdn.sparkfun.com/datasheets/Sensors/LightImaging/ML8511_3-8-13.pdf" style="color:var(--global-theme-color)">ML8511 Spec Sheet (EN)</a>
- <a href="https://akizukidenshi.com/goodsaffix/ML8511_manual.pdf" style="color:var(--global-theme-color)">ML8511 Spec Sheet (JP)</a>
- <a href="https://www.ishikawa-lab.com/RasPi_UV_ML8511.html" style="color:var(--global-theme-color)">Another project that uses the ML8511 (JP)</a>
