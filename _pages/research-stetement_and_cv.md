---
layout: archive
title: "Research Statement and CV"
permalink: /research-statement-and-cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Here you can find a brief version of my research statement. Alternatively, you can download a more comprehensive version of it (work in progress) and my [updated CV](https://ffasilva.github.io/files/frederico_silva_cv.pdf) as PDF files.

## Short research statement

My work focuses on the fundamentals of robotics, guided by the first principles of mathematics and mechanics. I am interested in developing model and control strategies that can exploit the structure and geometry of the environment to allow intuitive definition of the problem and ensure the safe execution of the task. The developed approaches can be applied to multiple classes of robotic platforms, ranging from simple robotic manipulators to complex self-reconfigurable robots assembling branched kinematic chains, to solve problems in unstructured and dynamic environments.

### Modular dynamic modeling

The dynamic modular composition (DMC) is a formalism for modeling complex branched robots, which consist of several subsystems composed of multiple rigid bodies. The high-level strategy is abstract enough to allow instantiation to different algebras (e.g., dual quaternion algebra, spatial algebra, Lie algebra se(3), etc.) according to what best fits the overall architecture and control applications. The DMC has a unified graph representation and requires subsystems to communicate only with their neighbors, exchanging information about the twists, twist time derivatives, and wrenches at the connection points between them. Thus, from a subsystem perspective, the remaining subsystems that integrate the chain can be regarded as black boxes, abstracting the complexities of local dynamic models and not demanding full knowledge of even their neighboring subsystems. This modularity also enables parallel the calculation of subsystems' dynamics, which allows applications in multithreading or decentralized architectures running in different machines.

| ![dmc-quadruped.jpg](https://ffasilva.github.io/images/dmc_quadruped.png) | 
|:--:| 
| *Complex robots can be divided into **subsystems** to simplify modeling and control. In the DMC formalism, each node in a graph represents an entire subsystem, and we can obtain the dynamics of the robot using a simple linear operation on the graph interconnection matrix.* |

|**References**|
|[Silva, Frederico Fernandes Afonso, and Bruno Vilhena Adorno. ‘Dynamic Modeling of Branched Robots Using Modular Composition’. Under review in the IEEE Transactions on Robotics, 22 July 2024. http://arxiv.org/abs/2208.01795](http://arxiv.org/abs/2208.01795)|

### Whole-body control

In addition to enabling more fluid and human-like movements, whole-body control simplifies problems by letting us define specifications at the task level. By applying these strategies, rather than focusing on the individual movements of each component of a complex robotic system (e.g., a mobile base and a robotic arm attached to it, or individual limbs of a quadruped robot), we can specify high-level goals (e.g., a desired pose for the end-effector, a desired wrench at a contact point with the environment, etc.) and generate motions that use all available degrees of freedom of the robot to perform such tasks.

I have worked with whole-body control of nonholonomic mobile manipulators using feedback linearization and dual quaternion algebra. I have also explored the application of dynamic models obtained through the DMC in wrench-driven end-effector control using a strategy based on attractors to guide the end-effectors of branched robots to desired poses. In common, all strategies employ task-level specifications that lead to intuitive definition of the goals, an essential feature for any robotic application.

|**References**|
|[Silva, Frederico Fernandes Afonso, and Bruno Vilhena Adorno. ‘Whole-Body Control of a Mobile Manipulator Using Feedback Linearization and Dual Quaternion Algebra’. Journal of Intelligent & Robotic Systems 91, no. 2 (3 August 2018): 249–62. https://doi.org/10.1007/s10846-017-0686-3](https://doi.org/10.1007/s10846-017-0686-3)|
|[Silva, Frederico Fernandes Afonso, and Bruno Vilhena Adorno. ‘Dynamic Modeling of Branched Robots Using Modular Composition’. Under review in the IEEE Transactions on Robotics, 22 July 2024. http://arxiv.org/abs/2208.01795](http://arxiv.org/abs/2208.01795)|

### Geometric representation of the environment and vector field inequalities

By employing a geometric representation of the environment, we can define both restricted zones that must be avoided by the robot, such as regions too close to a moving obstacle, and zones of interest for a task, such as a surface on which to place a cup. Given these, vector field inequalities (VFIs) provide a strategy to impose dynamic active constraints on robots. In contrast to potential fields, VFIs do not affect motions tangential to these zones. The only requirements are analytical expressions for the distance and distance derivatives between different relevant geometric primitives and a Jacobian relating those to the velocities of the robot joints.

When applied to a linearly constrained quadratic programming problem, VFIs ensure the safe execution of tasks in dynamic environments.

|**References**|
|[Marinho, Murilo Marques, Bruno Vilhena Adorno, Kanako Harada, and Mamoru Mitsuishi. ‘Dynamic Active Constraints for Surgical Robots Using Vector-Field Inequalities’. IEEE Transactions on Robotics 35, no. 5 (30 October 2019): 1166–85. https://doi.org/10.1109/TRO.2019.2920078](https://doi.org/10.1109/TRO.2019.2920078)|

### Bi-manual manipulation

The cooperative dual task space (CDTS) [4] simplifies the representation of bi-manual tasks by defining a relative reference frame, which can be used to coordinate the relative motion of the two robotic arms performing the task, and an absolute frame, which can be attached to the object being manipulated and used to specify its motion. The CDTS is also applicable to multi-manual manipulation tasks by defining one relative frame for each pair of arms and one absolute frame.

We have been recently working on an extension of this formalism to allow a more flexible specification of the relative and absolute frames according to the task. For instance, a leader-follower configuration better suits the task of hammering a nail, whereas a distributed configuration is desirable when carrying an object. Additionally, we are also taking into consideration the wrenches involved in the manipulation and using VFIs to impose safety constraints.

|**References**|
|[Adorno, Bruno Vilhena, Philippe Fraisse, and Sébastien Druon. ‘Dual Position Control Strategies Using the Cooperative Dual Task-Space Framework’. 2010 IEEE/RSJ International Conference on Intelligent Robots and Systems (Taipei, Taiwan), IEEE, 2010, 3955–60. https://doi.org/10.1109/IROS.2010.5650218](https://doi.org/10.1109/IROS.2010.5650218)|