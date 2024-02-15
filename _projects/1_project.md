---
layout: page
title: BeagleMAV
description: Hexrotor design enabling full 6DoF actuation.
img: assets/img/beaglemav_on_printer.jpg
importance: 1
category: Research
related_publications: true
---

<!-- Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    --- -->

Current multi-rotor designs typically arrange their propellers in the same plane, or with a small radially-symmetric inward tilt, in order to provide efﬁcient vertical thrust. This results in an under-actuated system that must roll and pitch in order to move laterally. Others have proposed and examined the beneﬁts of conﬁguring a 6-rotor airframe with tilted rotors such that thrust can be directly applied parallel to the ground, eliminating the need to roll or pitch. Existing investigations into such 6 degree-of-freedom control strategies begin with a rotor layout and orientations before analyzing the resulting performance.

This BeagleBone Micro Aerial Vehicle (BeagleMAV) platform instead, presents a method to find the optimum rotor orientations that maximize desired performance characteristics for given airframe parameters such as mass and motor characteristics. As part of the optimization process, the multi-rotor’s mixing matrix is calculated and used in the proposed performance metric describing the resulting multi-rotor’s available control authority in realistic situations {% cite strawson2021rotor %}.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/beaglemav_on_printer.jpg" title="MAV on printer" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Solidwokrs_white_front_4k.png" title="MAV Solidworks 1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Solidworks_white_iso_4k.png" title="MAV Solidworks 2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, 3D printed BeagleMAV prototype on 3DP printer. Middle and right, Solidworks render of BeagleMAV.
</div>

A set of techniques to systematically analyze and design the monocoque airframe of this hexrotor UAV system is also developed, starting from parametric analyses and testing of the off-the-shelf motors and propellers for selection {% cite strawson2021monocoque %}, and then the thruster axes orientations are canted and further optimized for achieving the capability of in-plane maneuverability and direct decoupled 6DOF control {% cite strawson2021rotor %}.

The landing and perching related mechanism and controls design is also of great interest in terms of the BeagleMAV’s application in search and rescue and sensor deployment in the post-disaster scenario with confined spaces and uneven surfaces. A novel soft-robotic gripper design is being developed and will be presented in the future publications, which integrates both the features of contact-driven deformation and tendon-driven actuation. The gripper consists of one or two pairs of tendon-driven compliant fingers, each pair equipped with a tendon winch driven by a servo motor, and a base plate to connect the gripper system to the vehicle main body. With its novel finger design, the gripper can grasp objects with various shapes and sizes with sub-second (~0.8s) actuation and can support loads of up to 20 N with a pair of fingers with its total weight of less than 100 g.


[![BeagleMAV Flight Demo](assets/img/BMAV_in_flight.png](https://www.youtube.com/watch?v=0P7kTeUToKM "BeagleMAV Flight Demo")

<div class="caption">
    BeagleMAV Test Flight Video.
</div>

