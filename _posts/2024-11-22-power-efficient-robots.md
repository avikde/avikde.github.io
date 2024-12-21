---
layout: post
title: Power-efficient autonomous mobile robots
categories: talk travel
---

I gave a [talk at OSU's CoRIS seminar](https://engineering.oregonstate.edu/events/power-efficient-autonomous-mobile-robots). It was a joy to visit OSU's Robotics department. The faculty are driven to solve problems grounded in the real world, in application areas ranging from under the sea to the peak of Mt. Hood.

Also, it was only partially raining on the day of the seminar (which I found out was a rarity). The [PNW](https://en.wikipedia.org/wiki/Pacific_Northwest) scenery is terrific and would be a great draw if it didn't mostly rain from September to May.

![OSU](/images/osu.jpeg)

## Modularity

In this talk, I started with my own intellectual interests in robotics, which was very much a bottom-up exploration of composition in robotics.

### Dynamic legged locomotion

As with I'm sure many others, as a young graduate student, I was inspired by the dynamic legged locomotion work at the MIT Leg Lab in the 1980's:

<iframe width="560" height="315" src="https://www.youtube.com/embed/Bd5iEke6UlE?si=AViCJ6zrZC46DjyS" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

In his thought-provoking [book](https://mitpress.mit.edu/9780262681193/legged-robots-that-balance/), [Marc Raibert](https://en.wikipedia.org/wiki/Marc_Raibert) articulated an intriguing idea called "Control of Running Decomposed into Three Parts." Researchers have been trying to understand when and how this may be possible, and how it generalizes, since then.

My Ph.D. advisor, [Dan Koditschek](https://directory.seas.upenn.edu/daniel-e-koditschek/), has been doing that for decades. In the 1990's, his research group built and impressive array of juggling robots (as a less-power-hungry proxy for cyclic dynamical behavior):

<iframe width="560" height="315" src="https://www.youtube.com/embed/u8I7EXXgTvk?si=uSNLnBbZqDBkDfYy" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

In the course of the juggling research, they introduced a formal idea of [sequential composition](https://deepblue.lib.umich.edu/bitstream/handle/2027.42/67990/10.1177_02783649922066385.pdf) with an intuitive but mathematically rigorous and useful idea:

![Sequential Composition in IJRR '99](/images/sequential_composition_ijrr99.png)

Analogously, we can retroactively label Raibert's "control in three parts" idea as an example of [parallel composition](/jerboa-hopping-video). While the term is not extremely common in the robotics literature, similar concepts appear with names such as "decoupled control". The idea has clearly been empirically useful, but [formalizing it](/hybrid-averaging) has been quite tricky with any degree of generality.

Sequential and parallel composition are a very intuitive idea with equivalents in programming and spoken language. Consider the example of generating spoken language -- instead of outputting the sounds corresponding to an entire sentence at once, we may want to start by assembling words from [phonemes](https://en.wikipedia.org/wiki/Phoneme), and assembling those into sentences. On the other hand, modern [deep learning speech synthesis](https://en.wikipedia.org/wiki/Deep_learning_speech_synthesis) may not have any such compositional properties, which is an intentional counterpoint that we will return to.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">I saw debates on whether GPT-4V can “solve” compositionality, so I spent my precious Friday afternoon benchmarking it on Winoground.<br><br>Tldr: NO it’s still far from solved (GPT-4V 38.0% vs PaLI 28.8% vs MTurk Humans 85.5%).<br><br>Colab w/ all results: <a href="https://t.co/ksaoBNU8i4">https://t.co/ksaoBNU8i4</a> <br><br>🧵(1/n)</p>&mdash; CLS (@ChengleiSi) <a href="https://twitter.com/ChengleiSi/status/1731047065382523332?ref_src=twsrc%5Etfw">December 2, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

### Modularity elsewhere

Deep learning did evolve from neural networks, which evoke biology right in the name. Biology has [inspired many of the working principles](/what-are-robot-dogs) of quadrupedal robots, including behavioral modularity.

Animals have an abundance of sensory inputs and muscle, but the number of task-level variables important to any particular task is a lot smaller [Ting (2007)](https://pmc.ncbi.nlm.nih.gov/articles/PMC4121431/). Going further, [Ting et. al. (2015)](https://www.sciencedirect.com/science/article/pii/S0896627315001579) argues that motor modules arise from neural plasticity in spinal structures that selective coordinate and co-activate multiple muscles.
The result is that animals can control tasks like balancing in a hierarchical fashion, keeping the dimension of the task-space control low.

![Modules in Biology](/images/modules_biology.png)

<!-- ![Modules in Biomechanics](/images/modules_biomechanics.png) -->

While robots typically have fewer actuators than an animal has muscles, each individual task will typically be overactuated for a general-purpose robot. For example, a humanoid robot will not need its arms to maintain a standing posture.

If we accept the presence of these motor modules, these patterns of activation could be re-used for different behaviors. Quoting [Ting et. al. (2015)](https://www.sciencedirect.com/science/article/pii/S0896627315001579):

> For example, there are substantial similarities in the most active muscles of motor modules used for walking at different speeds and for different balance strategies, although inter-individual differences also exist.

Making equivalences to the synthetic disciplines, there is a clear connection to the idea of re-using behavioral modules, as we showed with [Minitaur vertical hopper compositions](/vertical-hopper-compositions).

Putting it all together, I'd argue that there are equivalences between biology and robotics in three distinct aspects of modularity:

![Modularity is Everywhere](/images/modularity_everywhere.png)

### Benefits of modularity

If we agree with all that

Why do we need it?

* Address fundamental robotics constraints in power, force, and computation

How do we get it?

* Principled application of reduced-order models for design and control

, then moved to the motivation from real-world applications with Ghost Robotics

## Impacts of

![Energy](/images/energy.png)

https://www.technologyreview.com/2024/12/13/1108719/ais-emissions-are-about-to-skyrocket-even-further/

![Safety and Predictability](/images/safety_predictability.png)


[The Challenge of Compositionality for AI](https://compositionalintelligence.github.io/)