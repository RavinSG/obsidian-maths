---
aliases: []
tags: [paper]
---

# Risk Assessment for Mobile Systems Through a Multilayered Hierarchical Bayesian Network

## Abstract
The main goal of this work aims at developing *a three-layer framework* that can *assess* the *potential risks* in android mobile systems.

A *Bayesian risk graphical model* is proposed to model risks propagation in the layered risk architecture.

Integrating the *static analysis*, *dynamic analysis*, and *behaviour analysis* on a hierarchical framework, the risk states and its propagation at each layer are well modelled with Bayesian risk graph, which can quantitatively analyse risks both apps or mobile systems posed.

## Background

The capability of the Bayesian probabilistic model motivated us to perform risks analysis by analysing the likelihood of app (or system) compromise by chaining Bayesian rules in a three-layered framework

This work aims to develop a risk analysis framework to *systematically assess the potential risks* in mobile system. The hierarchical model decomposes risks at an app (or the system) with *inter-dependencies into three layers* (static analysis layer, dynamic analysis layer, and behaviour analysis layer).

The framework then combines all specific risks in a coherent way and to capture all possible causes of identified risks by applying a Bayesian risk graph.

The hierarchical Bayesian risk graph (HBRG) features:
1. Different with most existing static analysis, this model integrates the potential risks analysis over: static risk layer, dynamic risk layer, and behavioural risk layer
2. It can help the users to find the dominating risky causes
3. It is able to determine out-system cause effects (For two different mobile systems A and B, when A failed, it can analysis the probability that B will also fail) 
4. Risks scores, in order to well evaluate the potential risks in a mobile system, the model finally will scale each application with a risk-score as well as the whole mobile system

## Risk Modelling

The hierarchical risk analysis architecture is able to accurately identify vulnerabilities, and the Bayesian risk graph can capture the interdependencies among vulnerabilities posed on apps and mobile systems.

Combine the hierarchical risk analysis with Bayesian risk graph to accurately model the risk states, propagations, and transition.

![[Hierarchical_Bayesian_Risk_Graph_Model.png]]

The edge between nodes in the graph denotes the probabilistic causal dependencies.

Based on the DAG, an [[Bayesian Networks|Bayesian Network]] model could be created, in which each node maintains a conditional probabilities table (CPT). The parental nodes in the HBRG are assumed to be marginally independent.

The relations in the HBRGs denote the transition probabilities between nodes, which are classified into three: 
1. Intra-layer relation, it connects the nodes within a layer
2. Inter-layer relation covers the connections between two adjacent layer
3. Cross-layer relation, denotes the links bridge between behaviour layer and static layer

In order to reduce the computation complexity, a cross-layer relation is transferred into two inter-layer relation by adding a *virtual node* (e.g: node Da).

In HBRG, the model parameters (CPTs, transition probabilities) are always estimated using statistical learning algorithm.

This work uses the Gnome dataset to statistically learning risk features at the static, dynamic, and behavioural layers to build accurate CPTs.

- [[Bayesian Risks Graph|Bayesian Risks Graph Model]]
- [[Hierarchical Bayesian Risks Graph]]

## Hierarchical Risk Assessment with BRGs

Each app runs in isolation from all others apps, consequently, an app has not granted access to other apps resources. Apps can be granted permissions that are displayed to the user for approval before the app installation.

The hierarchical risk assessment framework is able to conducts three layers of in depth risk analysis for both apps and mobile systems.

- ### Static Risk Analysis
The static analysis is mainly to disassembling the binary file (APK) to check source code. In general, the static risk analysis performs an in-depth scan of an apps permission requests, API calls, and discrepancies between the two, including following components:
1. App-decompile into smali format
2. Information extractor
3. API calls parse
4. Permission analysis
5. Grouping of critical API calls
6. Embedded sources
7. Log monitor and parser

The main goal of static analysis is to statistically find ways to trigger potentially malicious or risk behaviours before the app runs. The output of static analysis could be used to guide the dynamic analysis or can be used as parameters in dynamic analysis.

- ### Dynamic Risk Analysis
In this layer, the framework mainly detects following risks and exploitation:
1. Intent-based risks
2. Intent spoofing
3. Component Analysis
4. Android Network Sniffing

- ### Behaviour Risk Analysis
By leveraging the risks found in the static, dynamic, and behaviour layers, the framework can discover hidden, risky behaviours within a mobile app or system.

Typical tests in this layer include:
1. Auto exercises apps at run-time
2. Perform credential auto-login
3. Collect network activity for both SSL and non-SSL activities
4. Determine if app launches other apps during run-time
5. Monitor read/write access to device directory and hardware
6. Abnormal behaviour detection

## Risk Score

The causal risks could be a compound of a set of sub-risks produced by the joint effect of other risks.

By use Bayesian theorem, a numerical analysis can be performed to find the probability for each causal-risk. By refining the [[Representation#^CPT|CPT]], the HBRG can determine,
1. The probability that there occurred an attack on an app (or system)
2. The probability of an app (or system) will fail

Given the risk values at each app (or system), a weighted risk score for each app (or system) can be easily calculate
$$
R_{S}^{w}= wP(S),\ \  (R_{S}^{W}) \in [0,3]
$$
in which $P(S) \in [0,1]$.

The $Risk\_Scores$ are classified into three categories: 
- $Low: [0.0-1.0)$
- $Medium: [1.0-2.0)$
- $Severe: [2.0-3.0]$ 

## Contributory Cause Tracking

- ### Independent Contributory Causes Tracking

Forensically, when a risk occur, it is important to find all contributory causes or the probability of causes that make it happened.

Assume $s = \{s_{1},s_{2},\dots ,s_{k}\}$ denotes a group of contributory causes of an attack. Then we have
$$
p(s|a) = \sum\limits_{i=1}^{N_{s}}\alpha_{k}(i)
$$
in which $N_{s}$ denotes the number of nodes that cause the attack $a$; the $\alpha_{k}$s are the forward variables.

Using the likelihood ratio, we have
$$
\begin{align*}
P(a|s) &= \frac {P(s|a) P(a)}{P(s)}\\
&= \frac {P(s|a) P(a)}{P(s|a)P(a) + P(s|\bar{a})P(\bar{a})}
\end{align*}
$$
