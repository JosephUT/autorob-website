---
layout: page
title: Assignment 2
parent: Assignments
nav_order: 3
---

# Assignment 2: Pendularm
### Due 11:59pm, Monday, February 13, 2023
<br>

Physical simulation is widely used across robotics to test robot controllers. Testing in simulation has many benefits, such as avoiding the risk of damaging a (likely expensive) robot and faster development of controllers. Simulation also allows for consideration of environments not readily available for testing, such as interplanetary exploration (as in the example below for the NASA Space Robotics Challenge). We will now model and control our first robot, the Pendularm, to achieve an arbitrary desired setpoint state.

<center>
<a href="https://youtu.be/vOssEL1xqNs" target="_blank">
<img src="/assets/images/asgn2/space_robotics_video.png" style="width:600px;heigh:auto"></a>
</center>

As an introduction to building your own robot simulator, your task is to implement a physical dynamics and servo controller for a simple 1 degree-of-freedom robot system. This system is 1 DOF robot arm as a frictionless [simple pendulum](https://en.wikipedia.org/wiki/Pendulum){:target="_blank"} with a rigid massless rod and idealized motor. A visualization of the Pendularm system is shown below. Students in the graduate section will extend this system into a 2-link 2-DOF robot arm, as an actuated [double pendulum](https://en.wikipedia.org/wiki/Double_pendulum){:target="_blank"}.

<center>
<img src="/assets/images/asgn2/pendularm.png" alt="Penduluarm browser window."
style="width:900px;heigh:auto"/>
</center>


## Features Overview
This assignment requires the following features to be implemented in the corresponding files in your repository:

- Euler integrator in "project_pendularm/update_pendulum_state.js"

- Velocity Verlet integrator in "project_pendularm/update_pendulum_state.js"

- PID controller in "project_pendularm/update_pendulum_state.js"

Points distributions for these features can be found in the project rubric section. More details about each of these features and the implementation process are given below.


## Implementation Instructions
The code stencil for the Pendularm assignment is available within the "project_pendularm" subdirectory of KinEval.

For physical simulation, you will implement several numerical integrators for a pendulum with parameters specified in the code stencil. The numerical integrator will advance the state of the pendulum (angle and velocity) in time given the current acceleration, which your pendulum_acceleration function should compute using the pendulum equation of motion. Your code should update the angle and velocity in the pendulum object (pendulum.angle and pendulum.angle_dot) for the visualization to access. If implemented successfully, this ideal pendulum should oscillate about the vertical (where the angle is zero) and with an amplitude that preserves the initial height of the pendulum bob.

Students enrolled will implement numerical integrators for:

- [Euler's Method](https://en.wikipedia.org/wiki/Euler_method){:target="_blank"}

- [Velocity Verlet](https://en.wikipedia.org/wiki/Verlet_integration#Velocity_Verlet){:target="_blank"}

For motion control, students in both undergraduate sections will implement a [proportional-integral-derivative controller](https://en.wikipedia.org/wiki/PID_controller){:target="_blank"} to control the system's motor to a desired angle. This PID controller should output control forces integrated into the system's dynamics. You will need to tune the gains of the PID controller for stable and timely motion to the desired angle for a pendulum with parameters: length=2.0, mass=2.0, gravity=9.81. These default values are also provided directly in the init() function.

For user input, you should be able to:

- select the choice of integrator using the [0-4] keys (with the "none" integrator as a default),

- toggle the invocation of the servo controller with the 'c' or 'x' key (which is off by default),

- decrement and increment the desired angle of the 1 DOF servoed robot arm using the 'q' and 'e' keys, and

- (for the double pendulum) decrement and increment the desired angle of the second joint of the arm using the 'w' and 'r' keys, and

- momentarily disable the servo controller with 's' key (and allowing the arm to swing uncontrolled).


## Optional Extensions
Of the 4 possible optional extension points, one additional point for this assignment can be earned by generating a random desired setpoint state and using PID control to your Pendularm to this setpoint. This code must randomly generate a new desired setpoint and resume PID control once the current setpoint is achieved. **A setpoint is considered achieved if the current state matches the desired state upto 0.01 radians for 2 seconds.** The number of setpoints that can be achieved in 60 seconds must be maintained and reported in the user interface. The invocation of this setpoint trial must be enabled a user pressing the "t" key in the user interface.

- Of the 4 possible optional extension points, two additional points for this assignment can be earned by implementing a simulation of a planar [cart pole system](https://en.wikipedia.org/wiki/Inverted_pendulum){:target="_blank"}. This cartpole system should have joint limits on its prismatic joint and no motor forces applied to the rotational joint. This cart pole implementation should be contained within the file "cartpole.html" under the "project_pendularm" directory.

- Of the 4 possible optional extension points, two additional points for this assignment can be earned by implementing a single pendulum simulator in maximal coordinates with a spring constraint enforced by [Gauss-Seidel optimization](https://en.wikipedia.org/wiki/Gauss%E2%80%93Seidel_method){:target="_blank"}. This maximal coordinate pendulum implementation should be contained within the file "pendularm1_maximal.html" under the "project_pendularm" directory. An additional point can be earned by extending this implementation to a cloth simulator in the file "cloth_pointmass.html".


## Project Submission
For turning in your assignment, push your updated code to the **master** branch in your repository.
