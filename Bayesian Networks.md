---
aliases: [BN, BNs]
tags: []
---

# Bayesian Networks

Despite the name, Bayesian networks do not necessarily imply a commitment to Bayesian statistics.

Indeed, it is common to use frequentists methods to estimate the parameters of the CPDs.

Rather, they are so called because they *use Bayes' rule* for *probabilistic inference*.

## Inference
The most common task we wish to solve using Bayesian networks is probabilistic inference.

![[Representation#^waterSprinkler]]

Consider the water sprinkler network, and suppose we observe the fact that the grass is wet. 

There are two possible causes for this: either it is raining, or the sprinkler is on. Which is more likely?

We can use [[Bayes Rule]] to compute the posterior probability of each explanation,
$$\begin{align*}
Pr(S=1|W=1) &= \frac {Pr(S=1,W=1)}{Pr(W=1)} = \sum\limits_{c,r}Pr(C=c, S=1, R=r,W=1)\\
Pr(R=1|W=1) &= \frac {Pr(R=1,W=1)}{Pr(W=1)} = \sum\limits_{c,s}Pr(C=c, S=s, R=1,W=1)
\end{align*}
$$
where,
$$
\begin{align*}
Pr(W=1) &= \sum\limits_{c,r,s}Pr(C=c, S=s, R=r,W=1)\\
&= (.5*.1*.8*.99)+(.5*.1*.2*.9)+(.5*.9*.8*.9)\\
& \ \ \ \ \ \ +(.5*.5*.2*.99)+(.5*.5*.8*.9)+(.5*.5*.2*.9)\\
&= 0.6471
\end{align*}
$$
## Explaining away

S and R become conditionally dependent given that their common child, W, is observed, even though they are marginally independent.

For example, suppose the grass is wet, but that we also know that it is raining. Then the posterior probability that the sprinkler is on goes down:
$$
Pr(S=1|W=1,R=1) = 0.1945
$$
This is called "*explaining away*". In statistics, this is known as Berkson's paradox, or "*selection bias*". 

Consider a college which admits students who are either brainy or sporty (or both!) Let C denote the event that someone is admitted to college, which is made true if they are either brainy (B) or sporty (S).

Suppose in the general population, *B and S are independent*. We can model our conditional independence assumptions using a graph which is a V structure, with arrows pointing down

![[BS_Graph.png]]

Now look at a *population of college students*. It will be found that *being brainy* makes you *less likely to be sporty* and vice versa, because either property alone is sufficient to explain the evidence on C. i.e 
$$
P(S=1 | C=1, B=1) \le P(S=1 | C=1)
$$
## Top-down and bottom-up reasoning

In the water sprinkler example, we had *evidence of an effect* (wet grass), and *inferred the most likely cause*. This is called diagnostic, or "bottom up", reasoning, since it *goes from effects to causes*; it is a common task in expert systems.

Bayes nets can also be used for causal, or "top down", reasoning. For example, we can compute the probability that the grass will be wet given that it is cloudy. Hence Bayes nets are often called "generative" models, because they specify how causes generate effects.

##### The rest - https://www.cs.ubc.ca/~murphyk/Bayes/bnintro.html
