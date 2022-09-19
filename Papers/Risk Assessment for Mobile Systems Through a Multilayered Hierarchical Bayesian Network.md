---
aliases: []
tags: [paper]
---

# Risk Assessment for Mobile Systems Through a Multilayered Hierarchical Bayesian Network

## Abstract
The main goal of this work aims at developing *a three-layer framework* that can *assess* the *potential risks* in android mobile systems.

A *Bayesian risk graphical model* is proposed to model risks propagation in the layered risk
architecture.

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
- 
