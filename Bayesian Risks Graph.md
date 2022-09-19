---
aliases: [BRG]
tags: []
---

# Bayesian Risks Graph

The process that one or more *vulnerabilities propagation* to one (or more) different threat(s) could be defined as a dependence graph.

The risk states or its propagation are usually constructed as a *Directed Acyclic Graph* (DAG) and the *transition between nodes* could be modelled with local *conditional probabilities*.

A DAG can be modelled with a Bayesian graph model $G=\{V,E\}$ in which the nodes $V$ denotes the variables of risks, and the edges $E$ denote relations between nodes that can be described with conditional probability distributions.

For each variable $S_{i}\in \mathbf{V}$, a conditional probability distribution $P(S_i|Pa(S_i))$ is used to describe the transition. The $Pa(S_{i})$ denotes the parent set of the $S_{i}$ in $\mathbf{G}$.

The BRG is a powerful but intuitive tool for modelling, analysing, and predicting risks in mobile systems.

A unique joint probability distribution over $\mathbf{V}$, could be verified to be
$$
P(S_{1},S_{2}, \dots , S_{n}) = \prod_{i=1}^{n}P(S_{i}|\pi_{i})
$$
$P(S_{i}|\pi_{i})$ denotes the conditional probability of $S_{i}$ given the condition of $\pi_{i}$.


## Conditional Probability Table (CPT)

See [[Representation#^CPT|CPT]]

## Hierarchical Risk Template

In mobile systems, a risk at least includes one of three basic properties:
1. *Behaviour Risk*, which includes the potential threats that based on the behaviour analysis
2. *Dynamic Risk*, it involves potential risks based on dynamic analysis, such as app activities, network activities, etc.
3. *Static Risk*, it includes the potential risks and threats based on the static analysis, such as malware, size analysis, permission analysis, virus matching, etc.
The risk template provides BRG a template that describes the basic potential risks of an app or a mobile system.

## Risk Attribute

An attribute is a binary random variable representing the state of an instance of a risk.

A risk $S$ is associated with a state $(S = 1; true)$ or $(S = 0; false)$. The probability that risk $S$ happens is $Pr(S = 1)$.

When an app (or system) is compromised means the risk state of the app (or system) is true$(S = 1)$. 

## Atomic Risk

Let $\mathbf{S}$ denote a set of risks, $\mathcal{A}: \mathbf{S} \times \mathbf{S} \rightarrow [0,1]$ denote a set of relationships in $\mathbf{S}$. Then given $S_{pre},S_{post} \in S$, we have a : $S_{pre}\mapsto S_{post}$ is called an atomic risk if,
1. $S_{pre} \neq S_{post}$ 
2. given $S_{pre}= 1$, $S_{post}=1$ with probability $\mathcal{A}(S_{pre},S_{post}) > 0$ 
3. $\nexists \ S_{1}, \dots ,S_{j} \in S - \{S_{pre},S_{post}\}$  

## Bayesian Risks Graph

A BRG is s a tuple $(S,\upxi,\mathcal{T})$, in which $S = R_{B} \cup R_{D}\cup R_{S}$ denotes the set of attributes from three risk layers: $R_{B}, R_{D,}\text{and } R_{S}$ denotes the risks from *behaviour layer*, *dynamic layer*, and *static layer* respectively. 

$\upxi \subseteq S \times S$ denotes the space of risks. A risk states pair $S_{pre}, S_{post} \in \mathcal{T}$ if $S_{pre} \mapsto S_{post} \in \mathcal{A}$. Furthermore, for $S_{i}\in S$, the set $Pa[S_{i}] =\{S_{j}\in S|(S_{j},S_{i}) \in \upxi\}$   

![[Atomic_Risks.png]]

The above image shows a simple BRG example, in which the risk $r_{a}$ could be caused by sub-risks $r_b$ and(or) $r_c$, iteratively $r_b$ could be redivided into $r_e$ and $r_d$, where $r_d$, $r_e$, and $r_c$ are atom risks and could not be further divided.

The basic idea of the BRG is to calculate the probability of $r_a$ according to its parental conditional probabilities.

## Risk Combination

For risk $S_{j}$ in a BRG we have $S_{j} \in S_{B} \cup S_{D}\cup S_{S}$, assume that $S_{i}\in Pa[S_{j}]$, then there are two kinds of possibilities for risk combination: **AND**-combination and **OR**-combination.

![[Risk_Combinations.png]]

The probability could be defined as:
$$
Pr(S_{i}|Pa[S_{i}]) = \begin{cases}
Pr(\cap_{S_{i}=1}(a_{i})), &AND \\
Pr(\cup_{S_{i}=1}(a_{i})), &OR
\end{cases}
$$
