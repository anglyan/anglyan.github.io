---
layout: post
title:  "My favorite papers: applying Monte Carlo methods to the study of matter"
categories: [favorite-papers]
---

This is the first of what I expect will be a series of posts highlighting favorite papers. Some are important, some are whimsical, some are niche, but they are all relevant to me.

In 1953 Metropolis, Rosenbluth, Rosenbluth, Teller, and Teller published a scientific paper that described what is now called the Metropolis algorithm to compute the properties of systems in equilibrium. That work, titled [*Equation of State Calculations by Fast Computing Machines*](https://doi.org/10.1063/1.1699114), established the rules through which we can evolve a complex system until reaching an equilibrium state.

![The original article](/assets/images/metropolis_paper.png){: style="display:block; margin-left:auto; margin-right:auto; width:80%;"}

This is just a fantastic paper: despite being more than 70 years old, in order to fully understand their contribution you need a solid command of statistical physics, which is uncommon today unless you happen to have taken an advanced course during college or grad school.

A twist is that, despite being called the Metropolis method, Metropolis' contribution focused primarily on the computer where the computations were run, which was the MANIAC at Los Alamos. The development and implementation of the algorithm was carried out by Marshall and Arianna Rosenbluth, who continued exploring other physical systems using this technique in subsequent works. Teller contributed some key ideas that helped shape the article, including the statistical physics angle of the work, but he did not continue developing this technique beyond this contribution.

Things that I really like:

- The computations presented in the paper can be easily reproduced.
- Each iteration took around three minutes, and each point in the paper took at least one day of computations.
- Although the Metropolis algorithm establishes that the probability of transitioning to a new state depends exponentially on the energy difference (normalized by the temperature of the system), the authors focused on a 2D hard-sphere model that did not require the computation of exponentials. This was undoubtedly a practical choice to accelerate the computations.
- The paper is written in such a way that advanced concepts such as the virial expansion for the equation of state of a fluid and their diagrammatic representation are almost taken for granted. You have to have a good foundation to fully understand the results of the paper.
- [Arianna Rosenbluth](https://en.wikipedia.org/wiki/Arianna_Rosenbluth) was a real badass as a programmer of these early machines.





