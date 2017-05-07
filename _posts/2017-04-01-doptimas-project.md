---
title: "D-OPTIMAS - <b>D</b>istributed <b>OPT</b>imization <b>M</b>ulti <b>A</b>gent <b>S</b>ystem"
layout: post
author: ravpacheco
lang: en
ref: doptimas-project
img: indigo/indigo.png
tag: projects
projects: true
summary: "Overview about D-OPTIMAS <i>Distributed multi agent system</i>, a software to solve optimization problems of different classes, developed during my master degree."
jemoji: ":memo:"
category: project
---

In optimization, many important problems are NP-hard which are very hard to solve via mathematical programming due to their computational nature. 

Despite this fact, several works have been proposed that present mechanisms capable of producing faster solutions including the multi-agent systems. 

During my master degree I developed the D-OPTIMAS - Distributed Optimization Multi-agent System, a distributed and flexible multi-agent system for solving optimization problems of different classes. D-OPTIMAS uses the actors model, an asynchronous and scalable concurrence paradigm, capable of executing a large number of agents in distributed processes. In this system, each agent is encapsulated by an actor and runs a specific metaheuristic in a reactive and isolated way, interacting with the others exclusively by message passing, i.e., all information exchanged between the agents follows a defined asynchronous communication protocol. 

Simulations are carried out using different classes of problems, including problems involving the EggHolder and XinSheYang functions, which are usually used as benchmark for continuous optimization methods and a combinatorial optimization problem, and the number partitioning problem. The results obtained show that D-OPTIMAS is able to produce solutions very close to the optimal value. 

In addition, actors model has proven to be a powerful tool for building scalable multi-agent systems, reaching a number of agents with two orders of magnitude higher than multi-agent systems using shared memory concurrence paradigm.


[Click here](https://goo.gl/KPcsZO) to see my complete dissertation about the D-OPTIMAS.