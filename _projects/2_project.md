---
layout: page
title: Dambot Mini
description: a project with a background image and giscus comments
img: assets/img/Dambot_Halloween.jpg
importance: 2
category: Research
giscus_comments: true
---

In a groundbreaking collaboration between the CHEI Lab of University of California, San Diego and the United States Army Corps of Engineers (USACE), a cutting-edge project known as DamBot Mini is set to revolutionize the world of dam inspection and maintenance. Developed as a part of a sub-task dedicated to advancing the capabilities of uncrewed ground vehicles (UGVs), the DamBot Mini project represents a significant leap forward in remote inspection technology and the creation of 3D digital twins for critical infrastructure.

Pengcheng Cao, Mechanical Engineering PhD student, and Dr. Falko Kuester, Full Professor and PI of CHEI Lab, brought forth the idea of developing a novel compact tunnel inspecting UGV in early 2023. This ambitious undertaking aims to kick off the development, integration, and field testing of the DamBot Mini, a specialized UGV designed to navigate the interior of dams and capture essential data. And later, it has been supported and sponsored by Jordan Klein and Anton Netchaev, Research Engineers at the U.S. Army Engineer Research and Development Center (ERDC). What sets DamBot Mini apart is its sophisticated sensor hardware and software stack, a fusion of cutting-edge technologies that make it a true marvel in the field of robotics and remote inspection.

Situation: Tasked with designing and building an autonomous mobile robot to survey subterranean and tunnel environments within a summer (3 months), which was a very challenging task as this was the first time I worked on robots driving in tough environments and with multi-sensor integration.

Task: My role was to manage the project team, oversee the development of the robot, ensure timely delivery, and hopefully deliver a high-quality research paper.

Action: I worked closely with the student interns working under me, learned and got help from the experts in this area, performed agile development iterations and documented all progresses and issues, and negotiated with stakeholders to secure additional resources.

Result: Successfully delivered the robot 1 week ahead of schedule. The robot was successfully deployed to survey the Mojave River Dam tunnel with no technical issues. We were also able to publish a relevant research paper on semantic segmentation from multi-sensor perception in the proceedings of 2023 IEEE Robotic Computing Conference (<30% acceptance rate).


```html
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="https://github.com/p5cao/p5cao.github.io/blob/master/assets/img/exp_setup.png" title="Dambot Mini Setup" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
```

[![LiDAR SLAM Demo](https://img.youtube.com/vi/nzN0d7lsuig/0.jpg)](https://www.youtube.com/watch?v=nzN0d7lsuig "Direct-LIO Experiment")

<div class="caption">
    LiDAR Test with Direct Lidar-Inertial Odometry.
</div>


[![Fused Mapping](https://img.youtube.com/vi/4DpNuhWKShw/0.jpg)](https://www.youtube.com/watch?v=4DpNuhWKShw "Fused Mapping Demo")

<div class="caption">
    Fused Mappiing with Multi-Modal Densor Stack and R3live.
</div>