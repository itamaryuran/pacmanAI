WELCOME TO PACMAN!
on this exercise i've implemented basic search algorithems for several pacman problems
in search.py you will find:

-depthFirstSearch (DFS):
 this DFS implementaion will continouesly develop new states of pacman if it reaches a dead end it will go bacwards till the it find an undevelopped configurarion. This algorithem will return the first path it finds that gets to the target state. It will not necceserly return the shorthest path!
 RUN: python pacman.py -l tinyMaze -p SearchAgent 
      python pacman.py -l mediumMaze -p SearchAgent
￼     python pacman.py -l bigMaze -z .5 -p SearchAgent

-breadthFirstSearch (BFS):
 This algoriithem will develop all the new states it reached at the same time, meaning it will return the shortest path found, this is of course an "expansive" algorithem since it develops a big amount of roads at the same time.
 RUN: python pacman.py -l bigMaze -p SearchAgent -a fn=bfs -z .5

-uniformCostSearch (UCS):
  Here, the algorithm will develop the state with the "cheapest" path to. this of course will return an optimal path.
  RUN: python pacman.py -l mediumMaze -p SearchAgent -a fn=ucs 
       python pacman.py -l mediumDottedMaze -p StayEastSearchAgent 
       python pacman.py -l mediumScaryMaze -p StayWestSearchAgent
       
 -aStarSearch (A*):
 The algorithem chooses the state to develop based of two factors, the cost of the path so far, along with the heuristic value of current state. The "Heurstic value" is the estimated cost for reaching the goal state from current state.
 RUN: python pacman.py -l bigMaze -z .5 -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic

On searchAgents.py you will find some chalenges the pacman had to go through:

-CornersProblem:
 here pacman has to go through all four corners of the bord. this problem uses BFS algorithem I implemented in order to find the shortest path to all four corners.
 RUN: python pacman.py -l mediumCorners -p SearchAgent -a fn=bfs,prob=CornersProblem

-cornersHeuristic:
 like the last problem, only using A* search and a heuristic I defined. this heuristic formula returns the largest manhatten distance from the array of all corners that have'nt been visited yet.
 RUN: python pacman.py -l mediumCorners -p AStarCornersAgent -z 0.5

-FoodSearchProblem:
 Here our goal is to eat all of the food on the bord with the minimal effort. I implemented a heuristic function that returns the amount of food remaining on bord.
 RUN: python pacman.py -l trickySearch -p AStarFoodSearchAgent 

-ClosestDotSearchAgent:
 this is an example for an unoptimal search. pacman needs to eat all food on bord but now he will act "greedy" and will go to closest food to him.
 RUN: python pacman.py -l bigSearch -p ClosestDotSearchAgent -z .5

Had a lot of fun solving these tasks. Run it on your computer to see more. Terminal commands for running every task are added below each one.

 
