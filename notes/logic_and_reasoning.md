#Logic and Reasoning#

## Intro ##
  * Logic and planning 
  * Logic is how we decribe the world, we capture what we want and ignroe what we dont want
  * To make conculsions, can reference the logic instead of having to go back to observations 
    * but lol the logic has to be true, or else conclusions will suck 

## Background and Expert Systems ##
  * AI started in 50s and 60s, writting better logics 
  * Mistake 1: Using only boolean (true or false) logic 
    * probability is the key
  * Mistake 2: wrote everything by hand
    * now we think data first, instead of writting rules by hand
  * Expert system algorithms, used throughout the world (not even considered AI anymore)
  * Future: learning from example, transfer learning, interactive planning (human machine teams)
  * Resolution algorthim, graph plan, value iteration (markov processing)

## Propositional Logic ##
  * BEAMJ
    * Burgalury, Earthquake, Alarm, Mary Calling, John Calling 
    * each can be true or false, belief is true/false/unknwon 
    * Locical constants (true/false) 
  * Ex. models   
    * (E v B) -> A : When theres an earthquake or burgalury then alarm is true 
    * A  -> (J ^ M) : When the alarmn goes off, John and Mary call 
    * J <--> M : when one is true, the other is true 
    * J <--> ¬ M : when one is true, the other is false
  * Syntax: 
    * -> Implies
    * <--> biconditionally implies (iff)
    * v or 
    * ^ and 
    * ¬ not (option L)
  * Terminology:
    * Valid: always true? 
    * satisfiable:can make true
    * unsatisfiable: always false 
  * Limitations
    * can only handle T or F, no uncertainty 
    * can only talk about events (not object properties or relationships)
    * no shortcuts 

## First Order Logic ##
  * Can solve the last two limitations above
  * World - entological commitments 
    * relationships, objects, functions
    * Facts
    * Facts
  * Beliefs - epsitomological commitments
    * T/F/?
    * T/F/?
    * [0...n]
  * Representation of logic
    * Atomic - problem solving 
    * Factored - variables 
    * Structured - relationships betweek objects (first order logic)
  * Models
    * Starts with a model
    * can have constants: not one to one, many to one 
    * Functions: mapping from object to object 
    * relations: 
  * Syntax
    * sentences T or F
    * terms describe objects 
    * example:
      * sentences :  vowel(A), Above(A, B), 2 = 2 
      * terms : A, B, 2 or x, y Number(A)
    * Opertors: v ^ ¬ -> <-> ( )
    * Quantifiers ∀x or Ey 
      * for all ∀ or there exits E 
      * ∀x Vowel(x) -> number of (x) = 1

## Vaccuum World ##
  * having two location 
  * Variables
    * A - location 1
    * B - location 2
    * V - vaccuum
    * D1 - dirt A 
    * D2 - dirt B 
  * Relations
    * Loc
    * Vacuum
    * Dirt
    * At (o,l) 

