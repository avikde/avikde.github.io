---
layout: post
title: Modular MPC for RoboBee (IJRR 2022)
categories: papers robobee
---

My second paper from my Harvard postdoc "[An efficient, modular controller for flapping flight composing model-based and model-free components](https://journals.sagepub.com/doi/full/10.1177/02783649211063225)" is out on IJRR. This paper was a culmination of learning numerical optimization and [microfabrication](https://www.micro.seas.harvard.edu/research) during my Harvard postdoc. The latter was especially challenging due to COVID making it impossible to have a collaborative lab where you can actually ask for guidance when you don't know how anything works.

While the results are relatively modest, the concepts are interesting in my opinion. Specifically, in [Kodlab](https://kodlab.seas.upenn.edu/) we thought that optimization-based methods could not be made modular or compositional. While in most research papers, that ends up being true, there are some notable exceptions. For example,

- Todorov: [Analysis of the synergies underlying complex hand manipulation](https://homes.cs.washington.edu/~todorov/papers/TodorovEMBC04.pdf), [Compositionality of optimal control laws](https://scholar.archive.org/work/p3eeysqkf5aenir6yge7rq3lce/access/wayback/https://proceedings.neurips.cc/paper/2009/file/3eb71f6293a2a31f3569e10af6552658-Paper.pdf)
- Kuindersma: [An Efficiently Solvable Quadratic Program for Stabilizing Dynamic Locomotion](https://arxiv.org/abs/1311.1839)

Fun fact: I initially went to Harvard intending to work with [Scott Kuindersma](https://scottk.seas.harvard.edu/), but he moved to Boston Dynamics basically the moment I joined. 😂

System architecture:

![Figure 1](/images/images_large_10.1177_02783649211063225-fig1.jpeg)



![Figure 10](/images/images_large_10.1177_02783649211063225-fig10.jpeg)

Hovering clips:

<iframe width="560" height="315" src="https://www.youtube.com/embed/RV9CJE_unHk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## Model-based template controller

### Template: upright rigid body

### Waypoint tracking MPC

Linearization and discretization.


## Wrench-gradient based inverse dynamics

Data-driven

### Kinematics features

![Figure 3](/images/images_large_10.1177_02783649211063225-fig3.jpeg)

![Figure 4](/images/images_large_10.1177_02783649211063225-fig4.jpeg)

[Robobee perching](https://www.science.org/doi/abs/10.1126/science.aaf1092):

![](/images/chira2016.png)

![Figure 5](/images/images_large_10.1177_02783649211063225-fig5.jpeg)


![Figure 7](/images/images_large_10.1177_02783649211063225-fig7.jpeg)
