---
title: What game theory teaches us about behavior
author: Adrish Banerjee
date: 2020-09-11 11:33:00 +0530
categories: [Game Theory, Behaviour]
tags: [behaviour]
math: true
image: /assets/img/sample/calvin-and-hob-prisoners-dilemma.png
---

In the United States, in the 1950s and 1960s, cigarette brands were frequently sponsors of television programs. This changed in 1970, when the _The Public Health Cigarette Smoking Act_ bill was introduced in congress,  after the 1964 report by the Surgeon General found that lung cancer and chronic bronchitis are causally related to cigarette smoking. Remarkly, the two major tobacco brands, which oligopolized the US Cigarette brands backed this bill, and after President Nixon signed  the bill into law, during the first year profits (on average) for cigarette companies increased by $91 million.

The rationale behind the Cigarette companies backing the bill can be found exploring standard problem in game theory called the prisoner's dilemma. The prisoner's dilemma has been called the *E. coli* of social psychology, and it has been used widely to research various topics such as oligopolistic competition and collective action to produce a collective good.[1]


## Prisoner's dilemma

Two members of a criminal gang are arrested and imprisoned. Each prisoner is in solitary confinement with no means of communicating with the other. The prosecutors lack sufficient evidence to convict the pair on the principal charge, but they have enough to convict both on a lesser charge. Simultaneously, the prosecutors offer each prisoner a bargain. Each prisoner is given the opportunity either to betray the other by testifying that the other committed the crime, or to cooperate with the other by remaining silent. The possible outcomes are:

1. If A and B each betray the other, each of them serves two years in prison
2. If A betrays B but B remains silent, A will be set free and B will serve three years in prison
3. If A remains silent but B betrays A, A will serve three years in prison and B will be set free
4. If A and B both remain silent, both of them will serve only one year in prison (on the lesser charge).

The generalized form for the above game is shown below

  |           | Cooperate | Defect    |
  |:----------|:----------|----------:|
  | **Cooperate** |    R, R   |   S, T     |
  | **Defect**    |    T, S 	|   P, P     |


Where,

- R is the payoff for cooperation
- T is the temptation payoff
- S is the sucker's payoff
- P is the punishment payoff

and,

_T_ > _R_ > _P_ > _S_


If both the players are perfectly rational (their sole intent is to maximize the payoff for one self) and there is no opportunity for punishment or reward outside of the game, **the dominant strategy (Nash equilibrium) is to always defect**, regardless of what the other player chooses. This is backed by the reasoning that  B will either cooperate or defect. If B cooperates, A should defect, because going free is better than serving 1 year. If B defects, A should also defect, because serving 2 years is better than serving 3. So either way, A should defect. Parallel reasoning will show that B should defect.

Interactions between organisms which have similar payoffs as the prisoner's dilemma are ubiquitous in the real world, involving all sorts of organisms ranging from bacteria to us. The classical game, however does not model that organisms typically have multiple interactions with each other, and retain information about their opponents behaviour in the past and can switch strategies based on previous interactions.



---
