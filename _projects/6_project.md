---
layout: page
title: killersquad
description: Creative PCB-based quadrotor course design
img: assets/img/quad.jpg
importance: 6
category: Fun
---



OVERVIEW: 
18 LED lights in total will be used on the board -- 13 on the top and 5 on the bottom. Note that we are not including the two indicator LEDs (1 red and 1 green) near the MCU in this note.

Trace width: 5mil (0.127 mm, same as our default trace setting) used.



DETAILS:

For width 0.127 mm (5 mil, same as our default trace setting), thickness 1 oz/ft^2, temperature 25 degrees Celcius, and length 100mm, the estimated trace resistance will be 0.382 Ohms, leading to a max voltage drop 0.382 Ohms*25 mA = 0.00955 V = 0.23% of the Voltage source. 


Ref: http://circuitcalculator.com/wordpress/2006/01/24/trace-resistance-calculator

We are choosing the LTST-C170 series of LEDs emitting red, yellow, and blue lights manufactured by LITE-ON Technology Corporation. The red, yellow, and blue LEDs are of the MFR number LTST-C170KRKT, LTST-C170KSKT, and LTST-C170TBKT respectively.  The layout of LEDs ( for X-type rotor layout) will be as follows: 

*****************************************************************************************  
Note: All the LEDs on the left will be driven by one MOSFET, and the ones on the right will be driven by another MOSFET.

Roughly speaking, we are using the red LEDs (warm color) as rear lights of our quad and the blue (cold color) indicating the foward direction.  LEDs will also be added on the left hand side of the main board to give a straightforward left direction.  The 5 LEDs on the bottom will tell the outline of our quad.

The LEDs on the left are connected to the PWM pin 9~ on the microcontroller (PB4 pin) via the mosfet from our custom library, which is the Si302CDS N-Channel 20V (D-S) mosfet provided by Vishay Siliconix. The LEDs on the right are connnected to the PWM pin 34~ on the microcontroller (PB6 pin) with a similar connection through another mosfet. We connect S-gate of the mosfet to pin 9~/34~ of the microcontroller, the G-gate to BAT_GND, and D-gate to all the parallel-connected LEDs. The total 18 LEDs will consume current of 450 mA, with 25 mA allocated to each to ensure at least 1.2 relative luminous intensity at high battery voltage(4.2V) and 0.9 relative luminous intensity at low battery voltage(3.7V). Each LED has a resistor serially connected to it to restrict the currents, and the power of LEDs is provided by V_BAT. We use the Ohm's law equation R = (V_source - V_LED)/I_LED to calculate the resistance required for choosing the resistors from DigiKey. 

The red and yellow LEDs have the maximum forward current (I_LED) of 25mA at maximum supply voltage (V_source) of 4.2V, which corresponds to 1.25 relative luminous intensity and the forward voltage (V_LED) of 2V. The anticipated serial resistor to be used here will be 88 Ohm. We are choosing the YAGEO RC0805FR-0786R6L resistor with 86.6 resistance to connect to the diode. We need in total 14 resistors of this type.

The Blue LEDs also have the maximum forward current of 25mA (mapped to 1.2 relative luminous intensity on the curve), with the correspondng forward voltage of 3.5V and maximum supply voltage(V_source) of 4.2V. So based on Ohms Law we need to connect the Blue LED with a serial resistor of 28 Ohm. We shall choose to use YAGEO RC0805FR-0728RL resistor with exactly 28 Ohm resistance. We need in total 4 resistors of this type. 

All the resistors are selected from the same series, Yageo RC, as the resistor in the custom library we built before, and also share the same mounting pad sizes and footprint. 


DESIGN REVIEW for OTHERS:

Antenna and Antenna Driver:
1. The wire connection for the antenna is right. However, mayber it's better to do an mimic placement on the board as given in the repo. More specifically,  capacitor C1 can be moved to right up to the Balun.
2. I noticed that the pours are only covering the area below the capacitor C1. In fact, you can cover C1, too. Then, the GND pad on C1 could be connected to the GND plane directly through a via or so. 
3. Since we prefer to have nothing around the RF area, then we should be careful about the signals A7, A5, A3, which are pretty close to the balun in your design.

Power and Ground:
1. Some parts of the power/ground pours are very narrow (<0.5mm). Display each layer separately and pay attention to those parts with a cross shape, usually sitting in the throughhole. For example, if you check your throughhole GND of the IMU rescue header, and display only the ground plane layer 2, then you can see that cross parts are less than 0.5mm, which is roughly 0.3mm. This happens to be your PWR net class trace width. Probably this is a bug in autorouting such that some power/ground traces may finally be part of the power/ground pours during the final steps of the pour optimization. A possible solution: reduce the traces layout for power/ground signal; instead, use a via to directly push it into a power/gound plane. By doing this, the cross connection in the throughhole will be generated using the default thick metals.
2. For the Highcurrent net class, I think you've set your via diameters too small. The drill size should give an annular ring diameter of 30mil with annular ring to be 25% of drill radius. Your drill diameter should be no smaller than 24 mil.


IMU:
1. The capacitors are lying too close to each other, this would be hard for you to drop your parts on your board. In fact, not all the capacitors are important and sensitive. So, just make sure the sensitive ones are placed as near as possible. 
2. The position of the IMU header should be refined to make sure that the IMU on the breakout board(https://www.adafruit.com/product/3387) is roughly in the center. It seems like you can move the header a little bit to the right.

Microcontroller:
1. Similar to the IMU, the capacitors arel lying too close to each other. Professor suggests to allow 1-2mm between parts to make assembly easy.

Power Supply:
1. 3V3 plane power plane is not running underneath the voltage regulator U5. Thus, it will take some distance to go from your regulated 3V3 output to your other 3V3 parts.
 

Mechanical:
1. The arm length (from the center of DC motor to the edge of the board is about 31mm) is O.K. but maybe too short since the radius of the propeller is 55/2=27.5mm.  
2. The direction of the battery header B2 should be taken care of since it is facing the upper left propeller, which is pretty close (I did a basic calculation which is about 12mm). You will be struggling then when you get your battery wires in.
3. For the "cup" holder, the open angle is about 90 degree, which is fine, but can be smaller for better hold. Also, maybe it's better to give a little cut inside the motor holder circle to allow a bit stretching when you are squeezing in your motors.
4. Orienting all your parts in the same direction makes assembly easier (notice this on the FCB and your remote board).

LEDs:
1. The calculation is questionable (your final computed through current is said to be 3.94mA, however, this will lead to a different forward voltage again instead of the 2.0-2.1V, which is not matching). Since the through current depends on the forward voltage, the reasonable way is: first, set your expected through current and find the corresponding forward voltage; then, basing on your forward voltage and source voltage, calculate the remaining voltage the attached resistor should undertake; finally, you will have the value of the resistor based on the remaining voltage and through current.

<div class="row" align = "center">
        <img src="https://github.com/p5cao/p5cao.github.io/blob/master/assets/img/flying_gif.gif" alt="flying in class"  width="560" />
</div>


<div class="row" align = "center">
        {% include figure.liquid path="assets/img/MCU_schematics.jpg" title="MCU schematics" class="img-fluid rounded z-depth-1" %}
</div>

<div class="row" align = "center">
        {% include figure.liquid path="assets/img/quad_schematic.png" title="quadrotor schematics" class="img-fluid rounded z-depth-1" %}
</div>

<div class="caption">
    MCU schematics and quadrotor system schematics.
</div>

