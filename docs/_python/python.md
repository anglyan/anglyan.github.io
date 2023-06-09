---
topic: python
---

# Python

This is a list of some of my projects in Python. It includes from small
scripts to medium size modules.

## spikingtorch

Implementation of backpropagation through spikes in [pytorch](http://www.pytorch.org). Link to the source code in github:
[spikingtorch](https://github.com/anglyan/spikingtorch)

## machball

Implementation of an absorbing Markov chain model for reactive
ballistic transport, including the simulation of self-limited growth
inside nanostructures. Link to the source code in github:
[machball](https://github.com/aldsim/machball)

## gris

Simple package for reading/writing bibliographic entries in RIS format.
Link to Python package. You can find the source code in github:
[gris](https://github.com/anglyan/gris)

While still bumpy, we used this package to extract the information in
our work on the [evolution of ALD research
community](http://www2.avs.org/symposium2017/Papers/Paper_TF-ThP35.html)

## dcel

This package implements a doubly connected edge list and a 2D polygonal
map with basic functionality for saving/reading from file and plotting
postscript and eps figures of the 2D maps. Source code though github:
[dcel](https://github.com/anglyan/dcel).

## fresnel

Package to simulate the simulation of light with surfaces and
multilayers. Source code available through github:
[fresnel](https://github.com/anglyan/fresnel).


## Others:

### python + beamer

This is a simple snippet to collect a series of image files on a pdf
slideshow using beamer.

The following
[gist](https://gist.github.com/anglyan/ac8511d49623b894c224d2605d296df2)
reads a csv file with three columns containing a filename, a title for
your slide and some description, and prints out latex output based on
the beamer package:

{% highlight python %}
{% raw %}
import csv

header = r"""
\documentclass[mathserif]{beamer}
\usetheme{default}
\begin{document}
"""

footer = r"""
\end{document}
"""

baseslide = r"""
\begin{frame}
\frametitle{%(title)s}
%(content)s
\begin{center}
\includegraphics[width=0.8\textwidth]{%(filename)s}
\end{center}
\end{frame}
"""

def parse_csv(filename):
    data = [row for row in csv.reader(open(filename, 'rU'))]
    slides = [create_slide(*row) for row in data]
    return slides

def create_slide(filename, title, content):
    slide = {}
    slide['filename'] = filename
    slide['content'] = content
    slide['title'] = title
    return (baseslide % slide)

if __name__ == '__main__':
    import sys
    print header + "".join(parse_csv(sys.argv[1])) + footer
{% endraw %}
{% endhighlight %}

Then the only thing that you have to do is to redirect the output to a
file, and use latex or pdflatex.

## fpython

### Transforming python into a pseudo functional programming language

fpython is the result of a simple experiment looking into using Python
to implement a small programming language based on variable and function
definitions. The right hand side of each assignment will be a Python
expression. However, except for import and output statements, all
expressions will be assigned to a variable or a function.

In Python, there are two ways of defining functions: using `def` and
`lambda`. Instead, in math the way you typically define a function is as
follows:

{% highlight python %}
>>> f(x)=sin(x)
{% endhighlight %}

fpython defines functions using this assignment syntax, and it
transforms the source into the corresponding Python code using `lambda`
functions.

This is an example of the fpython interpreter:

    fpython 0.1.0
    ... 100 years transforming Python 
    into a pseudo-functional programming language...
    >>> import math as m
    >>> f(x) = m.sin(x)
    >>> a = f(1)
    >>> print a
    0.841470984808
    >>> a
    fpython SyntaxError: not a valid assignment
    >>> ^D

### Implementation details

At the core of fpython interface is the
[code](http://docs.python.org/2/library/code.html%22) module of
python\'s standard library. This module defines the InteractiveConsole
class, which helps implement read-eval-print loops in Python. By
subclassing InteractiveConsole, our input is first transformed into
python code and this code is then pushed into the Python interpreter:

{% highlight python %}
class Fpython(InteractiveConsole):

    def push(self, line):
        if len(line.strip()) == 0:
            return False
        if line[-1] == '\\':
            self.lines.append(line)
            return True
        else:
            self.lines.append(line)
            line = '\n'.join(self.lines)
            self.lines = []
            name, dummylist, idlist, code = transform(line)
            if name == None:
                toklist = scan(line)
                if (strvalue(toklist[0]) not in Fpython.importkws
                        and strvalue(toklist[0]) not in Fpython.outputkws):
                    self.write("fpython Error: not a valid expression\n",
                            True)
                    return False
            line = code
            return InteractiveConsole.push(self, line)
{% endhighlight %}

As it is shown above, our `push` method handles line continuation. It
then passes the resulting source to `transform`, which takes care of
parsing the function definition and returning the modified source. If no
function is identified, `transform` returns `None` as the first element
of the tuple, in which case the first token is checked against the
import and output keywords.

Finally, we can use `Fpython` both as an interactive console or as an
interpreter:

{% highlight python %}
if __name__ == '__main__':
    if len(sys.argv) > 1:
        ic = Fpython()
        for line in open(sys.argv[1], 'r'):
            ic.push(line.rstrip())
    else:
        ic = Fpython()
        ic.interact(banner)
{% endhighlight %}

In total, less than 200 lines of code.
