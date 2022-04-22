# Gambler's Problem

## The problem

This problem is from the book "Reinforcement Learning: An Introduction (Richard S. Sutton and Andrew G. Barto)" that I am reading.
The problem is as follows :
  
  A gambler has the opportunity to make bets on the outcomes of a sequence of coin flips. If the coin comes up heads, he wins as many dollars as he has staked on that flip; if it is tails, he loses his stake. The game ends when the gambler wins by reaching his goal of $100, or loses by running out of money. On each flip, the gambler must decide what portion of his capital to stake, in integer numbers of dollars. This problem can be formulated as an undiscounted, episodic, finite MDP. The state is the gambler’s capital, s ∈ {1, 2, . . . , 99} and the actions are stakes, a ∈ {0, 1, . . . , min(s, 100−s)}. The reward is zero on all transitions except those on which the gambler reaches his goal, when it is +1. The state-value function then gives the probability of winning from each state. A policy is a mapping from levels of capital to stakes. The optimal policy maximizes the probability of reaching the goal. Let ph denote the probability of the coin coming up heads. If ph is known, then the entire problem is known and it can be solved, for instance, by value iteration.

## My comments

I first noticed that there was an error in the formulation of the problem. Indeed in the problem the set of actions contains 0, but in the case where the probability of head < 0.5 the policy be to choose 0 all the time and the game will be infinite. The solution is to start the action interval at 1.

The results show that the optimal policy Ph < 0.5 is to finish the game as soon as possible. When Ph > 0.5 the policy make the game last as long as possible.
