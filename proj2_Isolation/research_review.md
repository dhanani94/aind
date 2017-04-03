## Summary of DeepMind's AlphaGo Algorith ##
### Main Objective ###
The purpose of this project was to create an algorithm to have a game agent increase it's odd at winning at a game of Go against human champions or previously implemented agents. The 




go: Most challegening game, enourmous search space
value networks (eval board positon
policiy networks  (select move)
superviesed learning from human expert games 
trained by reinforcment learning fro mgames of self play
Combines this with Monte Carlo simulation
99.8% wining rate agains other go programs 

Possible sequrence of moves is b^d, chess has b = 35, d =80
where as go as b =250 and d =150. meaning exhaustive search isn't feasible

Position evaluation (something that could be done with Chess, Checkers, and Othello but not go) to reduce depth 

To reduce breath: policy function 

Currently, other agents are based on MCTS (monte carlo tree search) 

Neural networks: value function to evaluate positons, policy network for sampling actions (reduces breath and depth)

Supervised learning for polcy network, 30 million positions from KGS Go Server
Reinforcement learning of policy networks. 

At this point, using no search at all the RL policy network won 85% games aganist Pachi, where as just supervised learning only won 11% of games agains Pachi 

To use RL for value networks usiing the KGS data set led to over fitting, to mitigate this, the team generated new self-play data set (30 mullion distinct positons) each from separate game. This function was consistently more accurate than Monte Carlo rollouts using fast rollout policy (also 15,000 less computation)

Look ahead search using MCTS algo, during this, the leaf nodes are evaluated using the value network and a random rollout. Counting all the traversed edges, the edge most travesed is the selection. 

Assessment: 
When given 5 s of compution time per move, AlphaGo ranks 99.8% 
Against fan Hui, professional, Alpha Go won 5 to 0


Combining deep neural networks and tree sarch,, effective move selection and position evaluation functions for go 

