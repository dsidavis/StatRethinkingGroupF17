# General notes, questions, or comments - Chapter 2

**Statistical Rethinking Reading Group - Fall 2017**

## Exercises

2M1: Note - Calculating the product of probabilities can quickly run into
numerical issues. To avoid this, in practice posterior/likelihood probabilities are
computed on the log scale, where the calculations are more stable (ask
Duncan or Matt for the details of this).

All of the built in distribution functions in R  (e.g., dnorm, dbinom,
etc.) have an argument to return the
probability on the log scale. Additionally, tools such as Stan (which
rethinking uses behind the scenes) work with the log-probability by
default. Therefore, it is not a terrible idea to get used to thinking
about calculating using the log.

2M2: The step prior here is approximately correct, but due to the
resolution of the grid, shows the line at the boundary in the plot with a slight
slope around p = 0.5. In reality, this should be a vertical line, as
the probability goes to exactly zero at exactly this point. Just be
clear that the plot is not quite right.

2M3: ~~the intuition on the last part of of Bayes Theorem is not quite~~
~~correct. Rather, this quantity is the joint probability of all the~~
~~different circumstances under which land can occur, i.e. p(land) =~~
~~p(land) * p(earth) + p(land) * p(mars).~~ In practice, this is a
normalizing constant and we ignore it in most Bayesian methods. This
ends up being a life-saver, because in more complicated situations,
this term can be impossible to calculate (e.g., what is the
probability of an individual X occuring? Now what is the joint
probability of all the Xs?). 

Hugo: *Thanks for the catch. I fixed the reasoning and struck through what
doesn't apply anymore.*

2M4: This is related to the classic [Monty Hall
Problem](https://en.wikipedia.org/wiki/Monty_Hall_problem).

2H3: You should not be using an unstandardized probability here - you
can calculate every piece of Bayes Theorem exactly. 

2H3: People get really excited about Bayesian updating, but the key is
your answer should be the same between an updating approach and
calculating the posterior all at once. In practice, because of how we
estimate posteriors updating is almost always a bad idea if you have
the option to estimate the posterior from the full data. (ask Matt if
you want to know more.)
