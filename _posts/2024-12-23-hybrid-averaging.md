---
layout: post
title: Hybrid averaging (IJRR 2018)
categories: papers
---

_The paper corresponding to this article was published in 2018._

The [Jerboa](/jerboa-hopping-video) and [Minitaur vertical hopping](/vertical-hopper-compositions) papers both demonstrated the generative possibilities with parallel composition of reduced-order models. Both these projects were extensions of the [Raibert's intriguing concept](https://mitpress.mit.edu/9780262681193/legged-robots-that-balance/) of "control in three parts" for the MIT Leg Lab planar hopper.

However, it has been very difficult to formalize when this type of control may work. In some related work, it is called "decoupled control," but it is clear that any robotic system of practical value will not have a [decoupling property](https://math.mit.edu/~jorloff/suppnotes/suppnotes03/ls4.pdf). The hallmark of articulated mechanical systems is that energy can be transferred among different components.

In this project and paper, we proposed [hybrid dynamical averaging](https://journals.sagepub.com/doi/full/10.1177/0278364918756498) as a way to express 

### A step toward formalizing parallel composition

If the exact system dynamics don't show this property, is there any benefit to squinting and approximating the behavior somehow?

#### Dynamical averaging

All of the behaviors of interest are cyclic.

![Averaged limit cycle](/images/avg_limit_cycle.png){: width="400" }

![Limit cycle](/images/limit_cycle.png){: width="600" }

![Time-reversal symmetry](/images/time_reversal_symmetry.png){: width="600" }
