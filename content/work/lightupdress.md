---
title: Light-up dress
description: An LED strip controlled by Arduino attached to a dress
slug: lightupdress
tags: project
image: lightupdress.jpeg
---


<div align="center">

# Light-up Dress
  <nuxt-img src="lightupdress.jpeg" alt="dress" height="500px" width="300px"/>
</div>

<div class="text" align="center">

<p>
  A friend of mine who is a fashion designer came to me with a request to fit LED lights that changed color according to the ambient brightness level in the surroundings to her dress. The LED glows blue when the brightness is high, and red when the brightness is low.
</p>

<b-card align="centre" style="max-width:40rem;">
  
  <h2> Components used  </h2>
  
  <div align="left">
    <ul>
    <li> Arduino Pro-mini 5V/16Mhz </li>
    <li> 11.1V Li-Po Battery </li>
    <li> 12V RGB strip </li>
    <li> Light dependent resistor (LDR) </li>
    <li> Reference resistor for voltage divider with LDR </li>	
    <li> DC Mosfet driver (I used an IRF620 here) </li>
    <li> PCB </li>
    <li> DPDT Switch </li>
    <li> DC-DC buck boost step down converter </li>
  </ul>
  </div>
  
  
</b-card>

</div>


