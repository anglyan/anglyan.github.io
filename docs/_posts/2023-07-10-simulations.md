---
layout: post
title:  "Why models and simulations matter?"
date:   2023-07-10 00:50:51 -0500
categories: personal
---

Because in many cases you want to have quantiative explanations or
predictions for whatever you are doing. The moment that you have
a model that provides a good agreement with experiments, you know that
you have a firm handle on the problem at hand. The moment that a
model stops agreeing with your experimental results, you have
a new problem to solve.

Not all problems require models, though. If your goal is to synthesize
a material and you want to check its composition, a good experimental
design and understanding of the driving forces controlling your growth 
is most likely what you need. In those cases, you need a good mental
model rather than a mathematical model. Still, data analytics and
machine learning could be the right thing for you. When I talk
about models and simulations here, I am refering to models mainly
based on physics/chemistry and math.

### What do I need to get going?

1. Going back to the *fundamentals*. You don't need a supercomputer
   or a fancy simulation to get going. In many cases, going back to the basics, to
   essentially textbook-level equations can get you a long way. A lot of phenomena
   in physics/engineering/materials science are formulated using simple models or
   things like partial differential equations. Going back to the basics can get
   you a long way. I still do it, pretty much all the time.

2. Using *simulation tools*. Some problems cannot be solved using simple equations
   that have a nice closed or analytic solution. In that case, you probably need
   to use computational methods to set up your problem and get your results. You
   are in luck though: we live in a golden era where there are plenty of tools
   available that you can learn how to use to solve your questions without having
   to code them from scratch. Many of them are open source, which means that they
   are free to use. Good computing literacy is the most useful skill.
   
3. *Coding* your own simulation tools. You don't have a ready-made simulation to
   solve your problem. No biggie: there are tons of programming tools and
   libraries that can get you a long way. Some of them are proprietary tools that
   you can probably access at no cost through your institution or company. Think 
   Matlab or Mathematica. Many of them, though, are open source, which means that
   you can reuse them and adapt them to your own problems. This is probably the
   hardest path out there, but also the most powerful. Learning a useful
   programming language is a must.

### If you are really serious about simulations you should learn a programming language

Regardless of whether you can get away with Excel or pen and pencil, I cannot
emphasize enough how important it is for a scientist/engineer to learn how
to code. And you are really primed for it: one of the hardest aspect of learning
how to code is to find a motivation to do it. Otherwise it often becomes an
academic exercise that is likely to fail unless you have a strong driving
force (as we say in Spanish, the graveyard is full of good intentions).

In your case, you already have hundreds of interesting problems
that you can use as motivation to learn: reading files and automatically plotting
the data, building a simple simulation that you can validate with another tool or
an analytical solution, learning how to process data so that you don't have to
open a file, copy two columns, remove the headers and save it in a different file
manually. There are infinite possibilities.

So the obvious next question is: which programming language? The answer is:
whatever your community is using. And my default answer would be: Python. My own
trajectory was (starting in middle school way back then)
Basic -> C -> C++ -> Fortran -> Python -> Julia -> Rust, with
few exotic detours such as Scheme, Java/Jython, Clojure, and Haskell. And
I basically followed the needs/opportunities at the time: I had a computer that
did Basic, then someone lent me a book of C, my college offered a few credits
intro to C++, my group and collaborators worked with Fortran, another postdoc
pointed me to Python, and the rest were the result of my own explorations,
interests, and needs at work.

### Models and simulations are a great scientific equalizer

One final point: not everybody has access to state of the art experimental
equipment or funds to run an experimental lab with the tools you need to
make a research impact. However, in many fields (not all of them, though) you
can make an impact in your research community by answering the right
question with the right tool. And while it is true that few of us have
access to the computational resources required to run large simulations, a
model that is simple enough to run on a budget laptop and
that gets you 80% there has its value. 

Models and simple simulations can therefore be an equalizer in scientific
research, if you find a relevant problem that can be solved or at least partially
solved with models you can put together. It doesn't come for free though: in order
to get there, you will have to invest your time and brain power to get the
right skills, the background you need, and to identify the right challenge. But
at least there is a path.
