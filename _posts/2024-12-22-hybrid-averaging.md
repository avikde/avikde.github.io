---
layout: post
title: Hybrid averaging (IJRR 2018)
categories: papers
---

The [Jerboa](/jerboa-hopping-video) and [Minitaur vertical hopping](/vertical-hopper-compositions) papers both demonstrated the generative possibilities with parallel composition of reduced-order models. Both these projects were extensions of the [Raibert's intriguing concept](https://mitpress.mit.edu/9780262681193/legged-robots-that-balance/) of "control in three parts" for the MIT Leg Lab planar hopper. However, it has been very difficult to formalize when this type of control may work. In some related work, it is called "decoupled control," but it is clear that any robotic system of practical value will not have a [decoupling property](https://math.mit.edu/~jorloff/suppnotes/suppnotes03/ls4.pdf). The hallmark of articulated mechanical systems is that energy can be transferred among different components, which makes them expressive and capable, but also [difficult to analyze](https://en.wikipedia.org/wiki/Double_pendulum#Chaotic_motion).

In this project and paper, we proposed [hybrid dynamical averaging](https://journals.sagepub.com/doi/full/10.1177/0278364918756498) as a way to make progress toward making formal arguments about these complex systems.

### Dynamical averaging

Since the exact system dynamics are difficult to directly analyze, it's helpful to consider approximating the behavior somehow. To this end, we looked to the well-established theory of dynamical averaging ([Guckenheimer and Holmes](https://link.springer.com/book/10.1007/978-1-4612-1140-2)), which applies to cyclic dynamical systems.

The idea is that a dynamical system with a limit cycle can be viewed in terms of a single "fast" coordinate _along_ the limit cycle, and several _orthogonal_ "slow" coordinates. As an example, an oscillating spring-mass system conserves energy, so the total mechanical energy is clearly a "slow" coordinate (it doesn't change at all). A very slight generalization is a regulated oscillatory system, where the energy might vary as it stabilizes to its limit cycle.

These "fast/slow" dynamical systems can be approximated by averaging the _dynamics_ along the limit cycle:

$$
\dot x = f(x, t) \approx \bar f (x) := \frac{1}{T} \int_{t\in \mathscr{T}} f(x,t)
$$

By doing this, we have reduced the dimensionality of our system by one, and crucially, eliminated any variability in $$f$$ that "averages out" over a cycle. This has huge intuitive (and mathematical) implications that we will come back to below.

### Choosing coordinates

The spring-mass example above conveniently was two-dimensional, resulting in a singular slow coordinate that we easily identified with total energy. What happens when there are (for example) several coupled spring-mass oscillators, with total system dimension $$n$$?

This example is instantiated in a very real manner in the [Minitaur vertical hopping](/vertical-hopper-compositions) demonstrations, and can appear frequently in coupled mechanical systems.

Our idea here was to think about the different coordinates as being:

- A single fast coordinate identified as the system _phase_: the cyclic coordinate that increments at a near-constant rate
- A single slow coordinate identified as the system _energy_: an overall measure of the "amplitude" of the system
- $$n-2$$ slow coordinates identified as _phase differences_: the relative phase of different degrees of freedom of the system

These coordinates are related to (but not being formally connected to) [Hamiltonian phase space coordinates](https://en.wikipedia.org/wiki/Hamiltonian_mechanics). The phase differences intuitively arise when several degrees of freedom are coordinated together, as in a set of coupled oscillators.

A visual depiction of these coordinates, with $$n=3$$, is shown below, where the blue manifold corresponds to the energy [zero set](https://mathworld.wolfram.com/ZeroSet.html), and the red manifold corresponds to the phase difference zero set. We intuitively refer to these as the _regulated_ and _neutral_ sets:

![Limit cycle](/images/limit_cycle.png){: width="600" }

_Note that for mechanical second-order systems, $$n$$ must be even (twice the number of degrees-of-freedom); the $$n=3$$ is for illustration._

### Hybrid averaging

The major contribution of this paper was to prove that it is possible to extend dynamical averaging to hybrid systems. To do this, we used the [saltation matrix](https://arxiv.org/abs/2306.06862) to capture the effect of the hybrid reset near the limit cycle.

![Averaged limit cycle](/images/avg_limit_cycle.png){: width="400" }

### Symmetries and averaging

![Time-reversal symmetry](/images/time_reversal_symmetry.png){: width="600" }

_The [paper](https://journals.sagepub.com/doi/full/10.1177/0278364918756498) corresponding to this article was published in 2018._
