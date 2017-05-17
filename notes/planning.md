## Planning Project 

### Problem solving vs Planning
  * problem solving agent finds the best path to the goal, and then executes 
    * Not what we do in real life, we sense/react to the real world 
    * blindfolding goons and having them walk forward, usually fail 
    * need feedback from environment 

### Planning vs Execution
  * Stochastic environment - we don't know what an action is going to do
    * therefore we cant plan out the path from the start 
    * going through traffic light, different weather or not light is green
  * Multiagent - if there are other players that can get in the way 
    * can only know this during execution time, not planning time
  * partial observability - we don't know what state we're in 
    * do we have to take a detour 
    * lack of knowledge, unknown 
  * hierachical - low level steps to make up the steps 

### Belief States
  * vacuum cleaner problem, what if sensor was broken. We have no idea where we're at
  * we can box around the possible states that we're in and belief that we're in one of
    them 
    * now when we do actions, we know a litle more about our state 
  * conformant plans - reaches the goal without ever sensing the world 
    * ex. goal is to be in a clean location (just suck) 

### Partially Observable Vacuum Cleaner Example
  * Local Sensing
    * Can see what location it is in 
    * can see what is going on in the current location
    * Cant see what's up with any other location 
  * after an action, we can sense and split up the belief state  
  * Deterministic world - each of the inidividual world state maps into equactly one other
    one 
  * observation can't make us more confused thank you aready are. But it's possible to not
    learn anything new from observation

### Stochastic Enviroment Problem
  * Robot that has slippery wheels but the suck state always works.
  * actions can reduce uncertantity - multiple outcome for actions 
  * end up with larger belief state
    * given two states in a belief state, we can end up with like 4 states after an acton
      :O 
    * but just like deterministic world, observations will split the belif state
  * in other worrds, actions increase uncertainty and observations decrease uncertainty 
  * so some of the strategies that would work in deterministic world __might__ work in
    stochastic BUT there's no gauranteed way for finding a solution with this fucking
    uncertainty 
  * every finite number of moves might not work, so there's no finite number of moves we
    can do to solve this shit
  * infinite sequence of action? hmmm... 

### Infinite Sequences
  * we create a loop by action, observe (if we moved then next state, if not then repeat
    last two steps!) 
    * instead of [S,R,S] we're gonna do
    * [S, while A:R, S]
    * if stociacity is independent (sometimes it works, sometimes it doesn't) guaranteed at inifinity 

### Finding a Successful Plan
  * Via search 
    * instead of states, belief states 
    * branch (that may have its own branch) is a single plan 
  * unbounded when every leaf is a goal
    * then it doesn't matter which branch you take, you can get to the answer
  * bounded when there are no loops 
    * if there's a loop you don't know how many steps it took to get to the leaf 

### Problem Solving via Mathematical Notation
  * Deterministic
    * [A,S,F] A - action, S - start, F - finish 
    * Result(Result(A,A -> S),S, -> F) <-- Goals
    * if result of action to get to start state and the naction to get to F is in goals is
    true
  * Stociastic
    * instead of s1 = Results(s,a), we do b1 = Update(Predict(b,a),o) 

### Tracking the Predict Update Cycle
  * in the kindergarten world (things can be come dirty at anytime)
    * however, actions work 100% of the time
  * calculus of belief states, some of the belief states get really large 
 
### Classical Planning
  * state space k-boolean (2^k) 
  * representation language and facotring world into variables
    * vaccuum world: DirtA (T/F), DirtB (T/F), VacA (T/F) = 3^2 
  * world state is complete state 
  * Belief stat depends on enviroment 
    * complete assingment OR paritial assigmnet OR arbitrary formula
  * Action schema
    * example for fligts 
~~~
Action (Fly ( p,x,y ) )
    PRECOND: Plane (p) ^ Airport (x) ^ Airport (y) ^ At (p,x)
    EFFECT : not At (p,x) ^ At (y) 
~~~
 
### Progression Search
  * Start off in initial state 
  * go through various actions
  * progression state space search until hit the goal 
  * really popular right now because
    * goo heuristics are easy to come up with 
    * concrete plan states 
 
### Regression Search (backwards search)
  * Knowing goal state, search backwards (what actions go into the goal state)
  * find the effect for the action that matches the goal 

### Regression Vs Progression
  * since we know the goal, we don't have to try out ALL possiblities for the actions to get one
    step closer, we can just figure out what action is needed to get to the goal
 
### Plan Space Search
  * search through plans instead of states 
    * Plan: start --> finish 
    * add actions to plan to refine plan
      * Plan2: start --> action1 --> finish 
    * do until the plan is guaranteed to work
    * popularity was big in 1980s but now not done much 
 
### Sliding Puzzle
~~~
Action (Slide (t,a,b)
Pre: On(t,a) ^ Tile(t) ^ Blank(b) ^ Adj(a,b)
Eff: On(t,b) ^ not On(t,a) ^ Blank(a) ^ not Blank(b)
~~~
 
### Situation Calculus
  *
 

### Chapter 11 - AIAMA
  * Planning - coming up with actions that will achieve a goal
    * scaling up to complex planning problems 
  * The planning problem 
    * Traditional planning has issues with irrelevant actions 
    * also has problems with finding a good heuristic function 
    * problem solvers can't use problem decomposition.
  * nearly decomposable means the planner can work on subgoals independently, but needs to do some work to combine subplans 
  * STRIPS language 
    * representation of states
      - propositional literals: ( poor ^ unknown ) 
      - First order literals At(Plan1, Melbourne) ^ At (Plane2, india) [these must be ground and function free]
      - Closed world assumption, if not explicitly mentioned, then false 
      - Representation of goal - positive ground literals
        * like "Rich ^ Famous" or "At(P2, Tahiti)"
      - representation of actions (action schema) 
        1. action name/parameter list 
        2. precodndtion (function free postive literals that must be true) 
        3. effect (function free literal describing how the state changes when action executed) 
    * add list for positive literals and delete list for negative literals 
    * 
      



















































