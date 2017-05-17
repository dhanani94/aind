## Intro
  * Sometimes state space is SO large, search can't do much 
  * n-queens problem (set up queens in such a way that they can't attack each other)

## Traveling Salesman Problem 
  * Have to visit n cities and then return to the starting point. Have to visit all nodes 
  * NP hard (nondeterministic polynomial), exponentially difficult 
    * connect all the cities randomly, and then uncross all the paths that cross
    * can get really close to the optimal solution

## 4-Queens
  * Iterative improvement problem, no queen can be on the same verticle, horizontal, or diagonal
  * probably want to start with the queen with the most "attacks" 
  * the example was solved with 2 moves, search would have taken forever here

## 5-Queens
  * 

## n-Queens Heuristic Function
  * reduce the number of atacks per move
  * 

## n-Queens Local Minima
  * when the position has the least amount of attacks, any move will make more attacks than before.

## Hill Climbing
  * Queens is multidementional, point of this is to maximize the value of a line 
  * Can move left or right on the X axis
  * shoulder - on the hill up but flat
  * global maximum - the highest point 
  * local maximum - a high point on the graph 
  * "flat" local maximum, multiple points that are part of the local max

## Local Maximum
  * look to the left, goes down. Look to the right, goes down this is a local maximum
  * tallest peak is the global maximum 

## Random Restart
  * climb and restart until you find a bunch of local peaks, and then return the highest one 
  * taboo search: keep track of where you've been already and not repeat that search

## Step Size Too Small 
  * if at a shoulder, and the step size is too small, it might only see the shoulder
  * how many times should a flat line be okay 

## Step size too big
  * if the step size is too big, it might be that the hill gets passed
  * you could end up with a infinite loop (skipping the max and then oscilate) 
    * start with a big step size and then make it smaller as you go 

## Annealing
  * lowest enegry positons, like mudcracks, honeycombs
  * mimization done by design, iron molecule low energy states 
  * Idea of heating and cooling to get out of oscilation
  * increase and decrease randomness 

## Simulated Annealing
  * Formula: 
  * for t=1 to infinity do:
    * T <-- schedule(t)
    * if T=0 then return current
    * next <-- a randomly selected successor of current
    * if delta(E) > 0 then current <-- next
    * else current <-- next only with probablity e^(delta(E)/T)
  * English:
    * itrate looking for points to current points that have better value 
    * however, select points randomly in the region near us, if positon is better than curren postion, then take it. 
    * if new position is not better, than take it with a crazy weird probabilty 
    * in the beginning the temprature is high (moves randomly) then cools down when it gets to the peak and does a hill search 
  * guaranteed to find global max if start T big enough and cool it slow enough 

## Simulated Simulaed Annealing
  * 

## Local Beam Search
  * instead of one particle, we have K particles
    * unline random restart, the particles share info between iterations 
  * stociastic beem search, has some randomness 

## Representing n-queens 
  * encode by column, number represents how high up (row) the single queen is at

## Genetic Algorithms
  * there are 28 posibile pairs of attacking queens
    * 8!/(8-2)!\*2! = 28
  * good to know, because thats part of the fitness function (28 means we won!) 
  * Example
    * get four random boards, evaluate each boards based on fitness function 
    * porportional probability of how likely it is to breed (normalize to percentage)
    * then based on that probability, choose which boards can be parents
      * n parents make m babies by crossover (select random point to split parents. The children get a slice based on the split from each parent)
    * 

## GA Crossover
  * 

## GA Mutation
  * small chance that the digit will mutate into another digit, this adds some randomness and ensures that good features aren't lost forever 
  * randomness stociastic beam search 
  * 

## Method Similarities
  * reducing the randomness in mutation, but the method could do better
  * tuning crossover, number of parents etc. 
  * this is a version of stociastic beam search (but has an anaology with biology)
  * 

## Outro
  * could get stuck in local max, so we used randomness to fix this 
  * random restart, restart randomly
  * simulated annealing to cool of the randomness to get better 
  * genetic algoritm, select position based on fitness 
  * stociastic beam search, children get better 
## READINGS 
  * AIMA: Chapter 4.1
  * Further information 4.2 -4.5
## Lab (optional)
  * 






