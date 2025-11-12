---
layout: archive
title: "Active Projects"
permalink: /projects/
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

# Past projects

Those are the projects I have been involved in the past.

## REINE

Reconfigurable Robots for Inhospitable Environments (REINE) was a Marie Curie Postdoctoral Fellowship project under the UKRI Horizon Europe guarantee funding ([EP/Y024508/1](https://app.dimensions.ai/details/grant/grant.13905684)). This project was developed by Dr. Frederico Fernandes Afonso Silva, with the supervision of Dr. Bruno Vilhena Adorno at the University of Manchester.

### Modular dynamic modeling

The dynamic modular composition (DMC) is a formalism for modeling complex branched robots, which consist of several subsystems composed of multiple rigid bodies. The high-level strategy has a unified graph representation and is abstract enough to allow instantiation to different algebras (e.g., dual quaternion algebra, spatial algebra, Lie algebra se(3), etc.), according to what best fits the overall architecture and control applications.

| ![dmc-quadruped.jpg](https://ffasilva.github.io/images/dmc_quadruped.png) | 
|:--:| 
| *Complex robots can be divided into **subsystems** to simplify modeling and control. In the DMC formalism, each node in a graph represents an entire subsystem, and we can obtain the dynamics of the robot using a simple linear operation on the graph interconnection matrix.* |

The DMC requires subsystems to communicate only with their neighbors, exchanging information about the twists, twist time derivatives, and wrenches at the connection points between them.

|![dmc-backward.jpg](https://ffasilva.github.io/images/dmc_backward_propagation.png)| ![dmc-forward.jpg](https://ffasilva.github.io/images/dmc_forward_propagation.png)|
|:--:|:--:|
|*Forward propagation of twists from subsystem $p_i$ to the remaining subsystems of the branched robot. Hatched regions indicate the areas influenced by the twist at the connection point $a_i$.*|*Backward propagation of wrenches from subsystems $j \in S_i$ to the remaining subsystems of the branched robot. Hatched and crosshatched regions indicate the areas influenced by the wrenches at the connection points $b_{i,j}$.*|

Consequently, from a subsystem perspective, the remaining subsystems that integrate the chain can be regarded as black boxes, abstracting the complexities of local dynamic models and not demanding full knowledge of even their neighboring subsystems. This modularity also enables parallel the calculation of subsystems' dynamics, which allows applications in multithreading or decentralized architectures running in different machines.

|**References**|
|[Silva, Frederico Fernandes Afonso, and Bruno Vilhena Adorno. "Dynamic Modeling of Branched Robots Using Modular Composition". Under review in the IEEE Transactions on Robotics, 22 July 2024. http://arxiv.org/abs/2208.01795](http://arxiv.org/abs/2208.01795)|