---
aliases: []
tags: [paper]
---

# Dynamic Security Risk Evaluation via Hybrid Bayesian Risk Graph in Cyber-Physical Social Systems

## Abstract
The objective of this paper is to investigate associated risks in CPSS, and a hybrid Bayesian risk graph (HBRG) model is proposed to analyse the temporal attack activity patterns in dynamic cyber-physical social networks.

In the proposed approach, a [[Hidden Markov Models|Hidden Markov Model]] is introduced to model the dynamic influence of activities, which then be mapped into a Bayesian risks graph (BRG) model that can evaluate the risk propagation in a layered risk architecture.

## Background
Hundreds of millions of users that use social media are facing security threats, such as cybercrimes, identity stolen, device/social profile hacked, overconfidence.

Effective risk evaluation should be provided to help the social network platforms and users well understand the security situation they are facing, and accordingly, security and privacy protection solutions should be developed to help the users stay safe online

The social systems security are facing severe’ security challenges,
1. Most social systems are unable to secure the environment for users. These platforms are unable to provide a reliable system to identify duplicated or fraudulent accounts
2. Social network scamming is highly effective and lucrative. Only less than 20% of scams can be spotted by the professional users. The social networks provide unreliable “trustiness” for users, which may result in rampant scams spread rapidly
3. Cyber attackers/criminals can easily target specific victims through social networks. For example, the LinkedIn was a key recon tool for the cybercriminals who executed the Anthem data breach and its 80 million stolen records.

## Contributions
1. Develop a hybrid risk analysis model in cyber-physical social systems (CPSSs), in which a hidden Markov model ([[Hidden Markov Models|HMM]]) is introduced to *model the dynamic user activities* that can cause potential risks
2. A Bayesian risks graph ([[Bayesian Risks Graph|BRG]]) model is introduced in the top layer to analyse the potential risks that the activities can cause. The BRG model is able to classify the user activities into three levels (static, dynamic, and behaviour) and can dynamically evaluate the potential risks that caused by user activities
3. A node mapping scheme is proposed that can map the HMMs in the bottom layer to the Bayesian nodes in the BRG model

## Hybrid Bayesian Risk Model

- ### Threats and Risks in CPPS
Attackers can collect sensitive privacy information from users’ profile by combining different pieces of information in many different ways.

Generally, the possible attacks  can be grouped into two categories:
1. Vertical attacks that focus on a specific social network site or specific user
2. Horizontal attacks, which focus on the crosscorrelation networks to mine the sensitive information that might be useful for committing attacks.

The information might come from multiple different sources (such as social networks, emails, IoT, interested forums).

It is necessary to develop a security risk/threat analysis model by incorporating the social network influence as perceived by the users, which should be designed to be able to identify the major factor leading the security risks in real time.

- ### Hybrid Bayesian Risk Model

![[Hybrid_Bayesian_Risk_Model.png]]

The hybrid Bayesian risk model has a two-layer and interconnected architecture as shown above.

In the bottom layer, the HMM is used to model the activities of a user in the dynamic social network, which describes the states, observations, and the aggregation of influences of neighbouring nodes.

The [[Hidden Markov Models|HMM]] is powerful for modelling users’ activity evolution in social networks according to a Markov chain with a hidden state that is influenced by the collective activity of the neighbouring of the user.

Meanwhile, the [[Bayesian Risks Graph|BRG]] network is a probabilistic graphical model that represents a set of featured risks and their conditional dependencies via a directed acyclic graph (DAG).

## HMMs
Since the *user activity in social network*s has distinctly *non-Poissonian characteristics* furthermore, the *activities of neighbouring users* (followers, friends in social network) can significantly *affect user activity*, the HMM can well describe the user activity and explicitly take into account the *interaction between the users* by introducing a *coupling* between two *stochastic processes*.

The work in [[Information Integration via Hierarchical and Hybrid Bayesian Networks|paper]] shows that the coupling HMMs can well model a probabilistic process of status and the interactions between these activities.

- In social networks, the user activity has the following features:
	- The activity of users are dynamic
	- The individual activity may be preferentially affected by other linked users (such as followers, friends, or even some unlinked users)
	- The states of users are unobservable

The HMM is able to model the *hidden states*, which *correspond* to *different patterns in user activity*.

In social networks, the state transition can be influenced by its neighbours and it is possible to explain the observed data and predict the future activity of a user

With a learning model, the HMM can *cluster users* and find the resulting cluster structure *allowing* intuitive *characterisation* of the users in terms of the *interaction dynamics* between a user and their social network.

- In this paper, the user dynamic activity in a social network can be modelled by the following three components:
	1. User states
	2. Observation density
	3. Influence of neighbours

A tuple $H_{i}= \{{Q_{i}},\mathcal{T_{i}},{Z_{i}}\}$ is used to represent an HMM $H_{i}$

Let $t = \{t_{1}, t_{2}, \dots, t_{N}\}$ denote the time-stamps of a specific user’s activities over a given period of interest. The time duration $\mathcal{T} = \{\tau_{i}= t_{i}-t_{i-1}|i=1,2,\dots,N\}$

- ### User States
In an HBRG, $Q_{i}$ is used to denote the states of a user $i$, which could be active $(Q_{i} = 1)$ or inactive $(Q_{i}=0)$

Let $Q_{i}\ in \{0,1\}(i=1,\dots,N)$ denote the states of a user, the state of $Q_i$ is dependent only on $Q_{i−1}$, and we have
$$
\begin{align*}
P_{0}&= \begin{bmatrix}1-p_{0} & p_0\\
q_{0}& 1-q_{0}  \end{bmatrix}\\
\text{and} \\
P_{1}&= \begin{bmatrix}1-p_{1} & p_1\\
q_{1}& 1-q_{1}  \end{bmatrix}\\
\end{align*}
$$
in which $p_{0}$ and $q_{0}$ denote probabilities from the inactive state to the active state.

- ### Observation
The observations $\mathcal{T} = \{\tau_{1}, \tau_{2}, \dots, \tau_N\}$ are a *series of activities* among suspicious users, tweets, and things with a time stamp associated with each link between two entities in social networks.

- ### Influence of Neighbours
The evolution of $Q_i$ is also influenced by other users in social networks (such as friends, followers, etc.) through activities such as post, reply, like, retweet, and comment.

$Z_i$ is used to represent the influence of the neighbours, which can be described as
$$
P(Q_{i}|Q_{i-1},Z_{i}) = P_{0}(Q_{i}|Q_{i-1})\cdot(1 - \phi(Z_{i})) + P_{1}(Q_{i}|Q_{i-1})\cdot\phi(Z_{i}))
$$
in which $\phi(Z):Z\mapsto[0,1]$ is assumed as the simplified capture of the evolution of $Q_{i}$ 