---
layout: post
title: Vertical hopper compositions (IJRR 2018)
categories: papers quadruped
---

Extending the methodology for [hopping behaviors on Jerboa](/jerboa-hopping-video) to [Minitaur](/ghost-robotics-minitaur) required understanding how to compose monopedal hopping primitives onto a quadrupedal robot. To do this, we built on the old idea of virtual bipeds, but in a way that would be compatible with the formal guarantees of the [hybrid averaging framework](/hybrid-averaging) that we had been publishing at about the same time.

Using simple bottom-up, decentralized, decoupled controllers, we were able to show a wide range of gaits working stably on Minitaur, with pretty good performance:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ijnOCQOpC7k" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


### Virtual bipeds

The way we used the idea of virtual bipeds here was to "project" the coordinates roughly along the gray arrows, and "pair" the legs projected together.

![Virtual biped](/images/virtual_biped.png){: width="400" }

After this projection, we are left with a kind of planar bipedal system to analyze with three degrees of freedom, as shown in the right column above.

### Vertical hopper compositions

Focusing on the bound/pronk projection, the types of limit cycles for these two gaits look like the flows roughly resembling the following picture:

![Vertical hopping limit cycles pronk bound](/images/vh_pronk_bound.png){: width="250" }

Looking more closely the picture above, the axes in the plot are the "phases" of the two legs, a concept we talked about in the accompanying [hybrid averaging](/hybrid-averaging) paper. That identification now encourages us to think about our original quadruped as a pair of (vertical) hoppers "coupled" by a body.

The "coupling" is physically instantiated by the body itself, and its inertia properties have a significant effect on the type of coupling. The [center of percussion](https://en.wikipedia.org/wiki/Center_of_percussion) is a well-studied property of baseball bats, juggling clubs, etc. that relate impulses on one end of the object to the wrench on a different point along the object. We used this definition:

![Center of percussion](/images/center_of_percussion.png){: width="400" }

Intuitively, the location of the center of percussion, which is in turn related to the mass distribution of the object, affects the type of coupling between the two hoppers.

### Pronking and bounding

We showed using simulation, and by physically altering the inertia characteristics of sagittal-plane Minitaur by adding an "inertia bar" to its back, that we could indeed get both bounding and pronking limit cycles by programming its front and rear ends as completely independent vertical hoppers:

<iframe class="speakerdeck-iframe" frameborder="0" src="https://speakerdeck.com/player/5ac547a6c3e7425fb91576e190bdad34" title="Reactive coordination: stabilizing common  quadrupedal gaits without CPGs" allowfullscreen="true" style="border: 0px; background: padding-box padding-box rgba(0, 0, 0, 0.1); margin: 0px; padding: 0px; border-radius: 6px; box-shadow: rgba(0, 0, 0, 0.2) 0px 5px 40px; width: 100%; height: auto; aspect-ratio: 560 / 420;" data-ratio="1.3333333333333333"></iframe>

This is a bit of an extreme interpretation of the style of decoupled control originally pioneered by [Raibert](https://mitpress.mit.edu/9780262681193/legged-robots-that-balance/) and also demonstrated on [Jerboa](/jerboa-hopping-video), but it also has interesting implications on the possibility of [distributed control](https://en.wikipedia.org/wiki/Distributed_control_system) of legged robots. Another way to think about it is that we are formalizing [preflexes](https://en.wikipedia.org/wiki/Preflexes), which have historically played a pivotal role in the mechanical stabilization of animal and [robot](https://www.sciencedirect.com/science/article/abs/pii/S1467803904000398) locomotion.

_The [paper](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=m-A4ZdEAAAAJ&citation_for_view=m-A4ZdEAAAAJ:cWzG1nlazyYC) corresponding to this article was published in 2018._
