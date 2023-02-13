---
layout: page
title: Home
description: A course covering 
nav_order: 1
permalink: /
---

# AutoRob: Robot Operating Systems

ROB 320, ROB 511 & EECS 367, Winter 2023 at The University of Michigan
{: .fs-6 .fw-300 }

AutoRob is an introduction to the computational foundations of autonomous robotics for building modern robot operating systems and applications to perform mobile manipulation tasks. AutoRob covers fundamental concepts in autonomous robotics for the kinematic modeling of articulated robots and algorithmic reasoning for autonomous path and motion planning. These core concepts are contextualized through their instantiation in modern robot middleware systems, along with coverage of paradigms for interprocess communication. AutoRob covers some of the fundamental concepts in computing, common to a ([second semester](https://eecs281staff.github.io/eecs281.org/){:target="_blank"}) data structures course, in the context of robot reasoning, but without analysis of computational complexity. The AutoRob learning objectives are geared to ensure students completing the course are fluent programmers capable of computational thought and can develop full-stack mobile manipulation software systems.

Within the ([Michigan Robotics Undergraduate Program](https://robotics.umich.edu/academics/undergraduate/){:target="_blank"}), the AutoRob course can be thought of as an exploration into the foundation for reasoning and computation by autonomous robots -- and, more generally, how to build "brains for robots." That is, given a robot as a machine with sensing, actuation, and computation, how do we build computational models, algorithms, programming environments, and applications that allow the robot to function autonomously? Such computation involves functions for robots to perceive the world (as covered in Robotics 330 and EECS 467), make decisions towards achieving a given objective (this class), transforming action into motor commands (as covered in Robotics 310 and Robotics 311), and usably working with human users (as covered in Robotics 340). Computationally, these functions form the basis of the sense-plan-act paradigm that defines the discipline of robotics as the study of ([embodied intelligence](https://dspace.mit.edu/bitstream/handle/1721.1/6569/AIM-1293.pdf){:target="_blank"}), as described by ([Brooks](https://rodneybrooks.com){:target="_blank"}). Embodied intelligence allows for understanding and extending concepts essential for modern robotics, especially mobile manipulators such as the pictured ([Fetch](http://fetchrobotics.com/research/){:target="_blank"}) robot.

AutoRob projects ground course concepts through implementation in ([JavaScript](https://en.wikipedia.org/wiki/JavaScript){:target="_blank"})/[HTML5](https://en.wikipedia.org/wiki/HTML){:target="_blank"}) supported by the KinEval code stencil (snapshot below from Mozilla Firefox), as well as tutorials for the ROS robot operating system and the rosbridge robot messaging protocol. These projects will coverrobot middleware architectures and publish-subscribe messaging models, graph search path planning (A* algorithm), basic physical simulation (Lagrangian dynamics, numerical integrators), proportional-integral-derivative (PID) control, forward kinematics (3D geometric matrix transforms, matrix stack composition of transforms, axis-angle rotation by quaternions), inverse kinematics (gradient descent optimization, geometric Jacobian), and motion planning (simple collision detection, sampling-based motion planning). Additional topics that could be covered include network socket programming, JSON object parsing, potential field navigation, Cyclic Coordinate Descent, Newton-Euler dynamics, task and mission planning, Bayesian filtering, and Monte Carlo localization.


---


<div class="staff-row" >
<div markdown="1" class="staff-column">

# Instructor

{% assign instructors = site.staffers | where: 'role', 'Instructor' %}
{% for staffer in instructors %}
{{ staffer }}
{% endfor %}

</div>
<div markdown="1" class="staff-column">

# Collaborating Instructor

{% assign instructors = site.staffers | where: 'role', 'Collaborating Instructor' %}
{% for staffer in instructors %}
{{ staffer }}
{% endfor %}

</div>
</div>

{% assign graduate_student_instructors = site.staffers | where: 'role', 'Graduate Student Instructor' %}
{% assign num_graduate_student_instructors = graduate_student_instructors | size %}
{% if num_graduate_student_instructors != 0 %}

# Graduate Student Instructors

{% for staffer in graduate_student_instructors %}
{{ staffer }}
{% endfor %}
{% endif %}

{% assign teaching_assistants = site.staffers | where: 'role', 'Instructional Aide' %}
{% assign num_teaching_assistants = teaching_assistants | size %}
{% if num_teaching_assistants != 0 %}

# Instructional Aides

<div class="staffer-table">
{% for staffer in teaching_assistants %}
{{ staffer }}
{% endfor %}
</div>
{% endif %}

---

<!-- # Week 4 Schedule
{: #weekly-schedule }

{% for schedule in site.schedules %}
{{ schedule }}
{% endfor %} -->
