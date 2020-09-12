---
title: What game theory teaches us about behavior
author: Adrish Banerjee
date: 2020-09-13 01:33:00 +0530
categories: [Game Theory, Behaviour]
tags: [behaviour]
math: true
image: /assets/img/sample/calvin-and-hob-prisoners-dilemma.png
---

Back in the 1950s and 1960s, when cigarette advertising was legal in the United States, tobacco companies were major sponsors of television programs. In the late 60s, the _The Public Health Cigarette Smoking Act_ bill was introduced in Congress, after the 1964 report by the Surgeon General found that lung cancer and chronic bronchitis are causally related to cigarette smoking. Interestingly, the two major tobacco brands which oligopolized the US tobacco industry then endorsed the law, and after President Nixon signed  the bill into law, during the first year profits (on average) for cigarette companies increased by $91 million!

Let's look over why it was favourable for the tobacco industry when advertising was banned using a prisoner's dilemma game. Prisoner's dilemma is a standard game which is extensively used in game theory to understand decision making. It strips away the variations between specific situations in which people have a choice of cooperating or deceiving each other and has been called the *E. coli* of social psychology,  widely to research various topics such as oligopolistic competition and collective action to produce a collective good.


## Prisoner's dilemma

In the words of Albert W. Tucker, who formalized the game and came up with it's name, the game is the following,

>Two members of a criminal gang are arrested and imprisoned. Each prisoner is in solitary confinement with no means of communicating with the other. The prosecutors lack sufficient evidence to convict the pair on the principal charge, but they have enough to convict both on a lesser charge. Simultaneously, the prosecutors offer each prisoner a bargain. Each prisoner is given the opportunity either to betray the other by testifying that the other committed the crime, or to cooperate with the other by remaining silent. The possible outcomes are:

>1. If A and B each betray the other, each of them serves two years in prison
>2. If A betrays B but B remains silent, A will be set free and B will serve three years in prison
>3. If A remains silent but B betrays A, A will serve three years in prison and B will be set free
>4. If A and B both remain silent, both of them will serve only one year in prison (on the lesser charge).

The generalized form for the above game is shown using the payoff matrix below

  |           | Cooperate | Defect    |
  |:----------|:----------|----------:|
  | **Cooperate** |    R, R   |   S, T     |
  | **Defect**    |    T, S 	|   P, P     |


Where,

- R is the payoff for cooperation - 1 year in prison
- T is the temptation payoff - Being set free
- S is the sucker's payoff - 3 years in prison
- P is the punishment payoff - 2 years in prison

and the tuple _(x,y)_ represents the payoff's received by player 1 and 2 respectively. For example, if player 1 cooperates, where as player 2 defects, the payoff for the players is represented by the value in the top right cell, _(S, T)_ i.e. player 1 receives the sucker's payoff _S_, and player 2 gets the temptation payoff _T_. To be prisoner's dilemma game in the strong sense, the following condition also must hold for the payoffs:


_T_ > _R_ > _P_ > _S_


If both the players are perfectly rational (their sole intent is to maximize the payoff for one self) and there is no opportunity for punishment or reward outside of the game, **the dominant strategy and Nash equilibrium strategy is to always defect**, regardless of what the other player chooses. This is backed by the reasoning that  B will either cooperate or defect. If B cooperates, A should defect, because going free is better than serving 1 year. If B defects, A should also defect, because serving 2 years is better than serving 3. So either way, A should defect. Parallel reasoning will show that B should defect.

This however, does not factor in repeated interactions with the same player. In real world scenarios, typically multiple iterations of such games are involved with the same opponent, and players retain information about their opponents behaviour in the past and switch strategies based on previous interactions. For instance, in certain strains of bacteria, when nutrients are scarce, two clonal lines (A clonal line is just multiple bacteria with the same genetic makeup), may aggregate into fruiting bodies in order to reproduce. Now there are 2 parts of the fruiting body, one being the stalk and the other part is the one that actually fruits (reproduces). During this process, the strain that attaches disproportionately to the fruiting section has a higher reproductive success, and there are often attempts by one strain to cheat (temptation payoff). But what is also seen is that next time around, the other strain does not cooperate with the cheater.

A large part of social behavior is built around organisms either trying to get away with something or spotting someone else do the same. And animals are usually very good at detecting when they are being cheated, more so than at detecting random acts of altruism. Deception might have an advantage in a single game of prisoner's dilemma, but it's no longer the dominant strategy in the iterative version (Caveat: This is only true when the total number of iterations of the game is not known).

## When to cooperate and when to defect

Research on optimal strategies for the iterated prisoner's dilemma (IPD) was kindled by Robert Axelrod in the 1980s. He organized a tournament in which participants have to choose their mutual strategy again and again, and have memory of their previous encounters. Axelrod invited academic colleagues all over the world to devise computer strategies to compete in an IPD tournament. The programs that were entered varied widely in algorithmic complexity, initial hostility, capacity for forgiveness, and so forth.

In these repeated games, Axelrod observed that there was one simple strategy which always outperformed all other strategies in the long run, irrespective of the other player's strategy. The strategy is the following, start off by cooperating, and in subsequent rounds, simply mimic the oponent's strategy, or in other words **tit-for-tat**.

The plot below shows the payoffs (the line represents the mean across 5 rounds, each round had 200 games each, generated using the axelrod-python lib) for the different strategies.

<img src="/assets/img/sample/axl-tournament-results.png"/>

Axelrod analyzed the top performing strategies and determined the following characteristics for success,

- Be nice: cooperate, never be the first to defect.
- Be provocable: return defection for defection, cooperation for cooperation.
- Don't be envious: focus on maximizing your own 'score', as opposed to ensuring your score is higher than your 'partner's'.
- Don't be too clever: or, don't try to be tricky. Clarity is essential for others to cooperate with you.

However, there is a vulnerability in tit-for-tat - real world systems are not 100% perfect. In case of a mistake in perception (the other player wanted to cooperate, but mistakenly sent the wrong signal), tit-for-tat can spiral into infinite loop of retaliation. Soon, as Axelrod began to introduce small amounts of signal error in the tournaments, another strategy overtook tit-for-tat as the winner - forgiving tit-for-tat. Forgiving tit-for-tat adds an occasional cooperation irrespective of being cheated in the previous move, to escape the death spiral and re-establish cooperation. However, this made this strategy vulnerable to being exploited playing against players who donot have forgiveness in them.

Soon it became apparent that there existed one even better strategy - start off with tit-for-tat, if and only if N rounds pass without being exploited by the other individual, switch to forgiving tit-for-tat - **that's deciding to establish trust**. This solves for the problem of signal error, at the same time avoiding being too forgiving and being taken advantage of.

Given what you know about the prisoner's dilemma now, the answer to the initial question posed is trivial and left as an exercise for the reader :). Thanks for reading !

<img src="/assets/img/sample/george-bush-fool-me-twice.jpg"/>


## References

This post was inspired by and draws heavily from Dr. Sapolsky's lectures on the biology of behavioral evolution. Also, if you'd like to run the tournaments yourself, please checkout this <a href="https://axelrod.readthedocs.io/en/stable/">python lib</a> which contains a collection of 230 different strategies.

---
