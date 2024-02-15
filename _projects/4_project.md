---
layout: page
title: RAY the ROV
description: Design and Initial Test of a neutrally buoyant ROV.
img: assets/img/ROV_underwater.jpg
importance: 1
category: Fun
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

The use of remotely operated vehicles (ROV’s) in deep and shallow sea marine biological applications has been increasing with new advancements in robotics and 3D printing. One of such applications being the surveillance of coral reefs. Currently the  surveillance is often done by divers manually gathering data (imaging and collecting samples). An automated ROV would allow for a more thorough and lasting study of the marine ecosystem without the need for constant human interaction. This study describes the design, modeling, manufacturing and testing of a 3D printable, low cost  ROV which could be utilized to perform imaging of coral reefs and the marine ecosystem in shallow waters. The prototype built in this study was successfully tested in a swimming pool, reaching depth as far as 14 feet. There is much future work that has to be done to reach the full potential of the design as the automation, energy storage and energy generation are aspects that haven’t been fulfilled  in the current design. 

The primary functions that the ROV must perform include underwater navigation and video/image streaming for surveying of coral reefs. In order to have a successful ROV capable of underwater navigation, the craft requires the proper density to counteract buoyancy, multi-directional propulsion, and a reliable receiver to operate the thrusters. The ability to gather video/image data from underwater requires an onboard camera as well as an electrical connection for data transfer. This system must be completely waterproofed. The future intended design is for the ROV to be fully autonomous and capable of recharging through mounted solar panels. Taking the current design timeline into consideration, the prototype controls will be manually operated utilizing a tether attachment to a Arduino board on the ROV. The tether will also serve as the electrical conduit for image data transfer. The ROV design is inspired by the manta ray, with the wings being of similar shape.

The ROV will employ a central airtight cylinder to house the electrical hardware, batteries, motor controllers, and video camera. The cylinder will either be made of PVC or clear acrylic material. One end of the cylinder will be sealed with a clear acrylic dome for the camera. The other end will be fitted with a removable rubber plug that ensures a water tight seal. The 3D printed “wings” and keel structure will slide over the cylinder and have a clamped connection. Four thrusters will be mounted to the wings to provide a total of 4 degrees of freedom. An ethernet cable coupled with an arduino board will be utilized for control input and data streaming back to the ROV operator above water.



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/ROV_electronics_1.jpg" title="ROV electronics" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/ROV_payload.jpg" title="ROV payload" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/ROV_underwater.jpg" title="ROV neutrally buoyant" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left, electronics configuraton of ROV. Middle, ROV payload carrying mechanism. Right, ROV is neutrally buoyant.
</div>


<!-- <div class="row" align="center">
    [![BeagleMAV Flight Demo](https://img.youtube.com/vi/0P7kTeUToKM/0.jpg)](https://www.youtube.com/watch?v=0P7kTeUToKM "BeagleMAV Flight Demo")
</div> -->

<div class="flight-demo-video" align="center">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/MKEA58bmy7I?si=8SYiX7NR85zc5q3q" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</div>

<div class="caption">
    RAY the ROV Pool Test.
</div>

