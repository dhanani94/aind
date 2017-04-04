# Heuristic Analysis The three heuristic functions my progam consists of are listed as follows:

1. unsharedMoves
    * This function searches for all the possible moves for the game agent, as well as the oppponent. Then, the function
      will subtract the number of shared moves between the opponent and the player from the player's number of moves. A
      shared move is defined as a move that is in the legal_move_set for both the player and the opponent. 
2. unsharedMovesWeighted
    * this function will take the value from unsharedMoves and multiply it by two. Futhermore, the function will then
      add the number of shared moves to the result. This essentially gives an player's unshared move 2 points and a
      shared move 1 point.  
3. unsharedMovesPenalty
    * this function will take the value of the unsharedMovesWeighted function and subtract from the value the maxScore
      of the oppenent. The function gives 2 points for player only moves, 1 point for player and oppenant shared move,
      and -1 point for oppenent only moves. 

Out of the three functions, my program is going to be shipped with unsharedMovesPenalty. The tables below show it outperforming the other two algorithms. Running numbers, it outperformed the ID_Improved algorithm by 10.72%. In contrast, the unsharedMoves heuristic scored 2.15% worse and the unsharedMovesWeighted performed 0.72% worse. The reason why this is the heuristic of choice is because it factors in both the player and the opponent's scores. Additionally, unlike the algorithms discussed in class, this heuristic prioritizes the moves that provide maximum player only moves. 


## unsharedMoves Results
### *Student Avg: 67.86% | ID_Improved Avg: 65.71%*

|         |         |             |    |   | 
|---------|---------|-------------|----|---| 
| Match 1 | Student | Random      | 15 | 5 | 
| Match 2 | Student | MM_Null     | 14 | 6 | 
| Match 3 | Student | MM_Open     | 15 | 5 | 
| Match 4 | Student | MM_Improved | 12 | 8 | 
| Match 5 | Student | AB_Null     | 12 | 8 | 
| Match 6 | Student | AB_Open     | 11 | 9 | 
| Match 7 | Student | AB_Improved | 13 | 7 | 


|         |             |             |    |    | 
|---------|-------------|-------------|----|----| 
| Match 1 | ID_Improved | Random      | 15 | 5  | 
| Match 2 | ID_Improved | MM_Null     | 12 | 8  | 
| Match 3 | ID_Improved | MM_Open     | 10 | 10 | 
| Match 4 | ID_Improved | MM_Improved | 14 | 6  | 
| Match 5 | ID_Improved | AB_Null     | 14 | 6  | 
| Match 6 | ID_Improved | AB_Open     | 14 | 6  | 
| Match 7 | ID_Improved | AB_Improved | 16 | 4  | 


## unsharedMovesWeighted Results
### *Student Avg: 70.00% | ID_Improved Avg: 69.29%*

|         |         |             |    |   | 
|---------|---------|-------------|----|---| 
| Match 1 | Student | Random      | 17 | 3 | 
| Match 2 | Student | MM_Null     | 14 | 6 | 
| Match 3 | Student | MM_Open     | 11 | 9 | 
| Match 4 | Student | MM_Improved | 18 | 2 | 
| Match 5 | Student | AB_Null     | 11 | 9 | 
| Match 6 | Student | AB_Open     | 12 | 8 | 
| Match 7 | Student | AB_Improved | 14 | 6 | 

|         |             |             |    |    | 
|---------|-------------|-------------|----|----| 
| Match 1 | ID_Improved | Random      | 16 | 4  | 
| Match 2 | ID_Improved | MM_Null     | 16 | 4  | 
| Match 3 | ID_Improved | MM_Open     | 9  | 11 | 
| Match 4 | ID_Improved | MM_Improved | 12 | 8  | 
| Match 5 | ID_Improved | AB_Null     | 16 | 4  | 
| Match 6 | ID_Improved | AB_Open     | 14 | 6  | 
| Match 7 | ID_Improved | AB_Improved | 15 | 5  | 


## unsharedMovesPenalty  Results
### *Student Avg: 70.71% | ID_Improved Avg: 81.43%*

|         |         |             |    |   | 
|---------|---------|-------------|----|---| 
| Match 1 | Student | Random      | 20 | 0 | 
| Match 2 | Student | MM_Null     | 16 | 4 | 
| Match 3 | Student | MM_Open     | 16 | 4 | 
| Match 4 | Student | MM_Improved | 17 | 3 | 
| Match 5 | Student | AB_Null     | 15 | 5 | 
| Match 6 | Student | AB_Open     | 16 | 4 | 
| Match 7 | Student | AB_Improved | 14 | 6 | 

|         |             |             |    |    | 
|---------|-------------|-------------|----|----| 
| Match 1 | ID_Improved | Random      | 16 | 4  | 
| Match 2 | ID_Improved | MM_Null     | 17 | 3  | 
| Match 3 | ID_Improved | MM_Open     | 8  | 12 | 
| Match 4 | ID_Improved | MM_Improved | 13 | 7  | 
| Match 5 | ID_Improved | AB_Null     | 16 | 4  | 
| Match 6 | ID_Improved | AB_Open     | 14 | 6  | 
| Match 7 | ID_Improved | AB_Improved | 15 | 5  | 


