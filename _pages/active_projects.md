---
layout: archive
title: "Active Projects"
permalink: /projects/active_projects
author_profile: true
---

<!-- Remove all borders from all tables in this page -->
<style>
  table {
    border: none !important;
  }

  table td {
    border: none !important;
  }

  table th {
    border: none !important;
  }

  table thead {
    border: none !important;
  }
</style>

<!-- Force columns to be of the same size in all tables in this page -->
<style>
table th:first-of-type {
    width: 10%;
}
table th:nth-of-type(2) {
    width: 10%;
}
table th:nth-of-type(3) {
    width: 50%;
}
table th:nth-of-type(4) {
    width: 30%;
}
</style>

Those are the projects I am currently leading or participating in.

## Robotic Laser Cutting

This project aims to develop adaptive control strategies for robotic laser cutting with applications to nuclear decommissioning. Adaptive control is used to estimate the laser torch's pose and [vector field inequalities](https://ffasilva.github.io/research/#VFIs) prevent collisions with the table and the box.


| <video width="80%" autoplay> <source src="https://ffasilva.github.io/videos/rlc_circle.mp4" type="video/mp4"> Your browser does not support HTML video. </video> |
|:--:|
| *Robotic manipulator UR3 following a circular trajectory to cut a box. Adaptive control is used to estimate the laser torch's pose. On the real robot, a camera will be used to retrieve this information.* |

For the experiments, a camera will be used to track the laser torch and the box; thus, allowing the system to react to changes in the environment.