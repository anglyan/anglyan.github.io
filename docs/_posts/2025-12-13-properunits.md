---
layout: post
title:  "Side project: properunits version 0.1.0 is out"
categories: python
---

Everybody has to deal with physical units. Pressure is one of my favorite examples. In addition to
the usual assortment of bar, torr, atm, and the humble Pascal, here in the US we have to deal
with things like PSI, which is pounds per square inches, or inches of mercury (inHg).

This is an issue when trying to write code dealing with physical systems. A quick perusal of Python packages
shows a zoo of possible solutions designed to help you do operations with physical magnitudes. To add
to the confusion, here is a new stable release of my side project: [properunits](https://pypi.org/project/properunits/).

## Intro to properunits

The core idea of properunits is that dealing with physical magnitudes should simply be an IO problem. A
user (me) wants to work with a specific unit and my code wants to work with its own unit. Once you
do that transformation, you should be good to go because you have transformed your 5 gallons into a
number using the proper units your code can work with. In my case, this means working with SI+ units,
which to me it means SI units plus maybe one or two exceptions.

So this is how it works:

```py
from properunits import Temperature

my_temp = Temperature(20, 'C')
the_proper_temperature = my_temp.x
```
What properunits does is provide a consistent interface to transform an input with user-defined units into
a proper value (in the example K) that my code can deal with.

You can know which unit is considered a "proper unit" by querying:

```py
my_temp.unit
```
which would return the string `'K'`.
Or, if you need to remind yourself which unit did you use, you can retrieve the original value through:

```py
temp, unit = my_temp.value
```

You can check the list of physical units available via:
```py
my_temp.list_units()
```

The documentation for propertunits can be found [here](https://properunits.readthedocs.io/en/latest/index.html)

## What properunits does not do

Basically anything else. I wanted to have something that would allow me to connect the experimental side of
my research with the models and simulations I create. I just needed to solve the IO problem, not to be able
to work with arbitrary units. I may entertain in the future the idea of being able to use other units as
the "proper unit", but I must admit it is fairly low in my priority list.
What I may do is expand the range of units to include specific use cases, like nautical miles and the like.

