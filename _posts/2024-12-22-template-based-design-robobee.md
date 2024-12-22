---
layout: post
title: Template-based design for RoboBee (IROS 2020)
categories: papers robobee
---

While there have been numerous projects where I've utilized reduced-order models for control, this is the first published one where I've been able to use them for optimizing robot design. It is also applied to a fairly complex system, the [RoboBee](https://en.wikipedia.org/wiki/RoboBee), justifying the effort expended into developing numerical methods for design.

### System architecture

The overall system architecture of the system is captured in the following diagram:

![Idea](/images/tbd_idea.png){: width="800" }

The starting points for this method are a template model, and a task. In this case, the task is flapping, and the model is the [blade element model](https://en.wikipedia.org/wiki/Blade_element_theory) applied to flapping wings. Those two, in conjuction give us a dynamical trajectory, with kinematics and interaction forces with the environment.

These kinematics are obviously parameterized by the parameters of the model that generated them. For example, if a flapping wing has more inertia, we can expect a smaller angular amplitude when subject to the same flapping torque.

For our design optimization, we non-dimensionalize the times and lengths in the trajectory. With this non-dimensional trajectory $$y(t)$$, and a parameter vector $$p$$, we utilize the fact that in mechanical systems, the dynamics are affine in $$p$$, i.e. the dynamical equations of motion can be written in the form

$$
U(y + \Delta y) f(p) = 0.
$$

This fact underpins classical [adaptive control](https://en.wikipedia.org/wiki/Adaptive_control), and in our case here, allows us to establish a bilinear constraint between state and parameter variables.

So, the design optimization problems attempts to find paramters that can minimize energy consumption, or another objective specified in $$\phi(p)$$, while minimizing the deviation from the desired trajectory $$\Vert \Delta y \Vert$$, and constrained by the system dynamics.

![Objective](/images/tbd_objective.png){: width="600" }


![Results](/images/tbd_results.png){: width="800" }

TODO: get from RI seminar slides

_The [paper](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=m-A4ZdEAAAAJ&sortby=pubdate&citation_for_view=m-A4ZdEAAAAJ:ODE9OILHJdcC) corresponding to this article was published in 2020._
