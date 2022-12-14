# Fall 2022 CS170 Project Skeleton
This repository contains utility functions which might be helpful for solving the project.

## Problem Statement
Summary: Given a weighted, undirected graph, construct a graph coloring that minimizes the given cost function, which can be found in either the project spec or starter.py.  
Read the full project spec here: [CS170 Fall 2022 project spec](https://github.com/WinsonTsangWan/CS170-project/blob/master/CS170_project_spec.pdf)

## Requirements
`python >= 3.6` is needed for `starter.py`, which contains a handful of utility functions, to run properly; it was, nevertheless, developed in python 3.9.  
Jupyter Notebook is required should you prefer using `main.ipynb`.

## Licence
Copyright 2022, The Regents of the University of California and UC Berkeley CS170 Staff  
All rights reserved.  
This content is protected and may not be shared, uploaded, or distributed without prior permission. 

## Reflection
The algorithm that we developed is a greedy graph traversal algorithm. We begin by assigning each node to a team (different methodologies for assigning initial teams that we tried include DFS'ing through the graph or iterating through the list of nodes and assigning each node to the smallest adjacent team, DFS'ing or iterating through the nodes and assigning each node to the smallest overall team, and randomly assigning teams). Then, we visit every node again (either by DFS or iterating through the list of nodes), and then reassign that node by choosing between the smallest adjacent team and the smallest total team; we make this decision by changing the node's team to both options, scoring the resulting graphs, and then choosing the team that results in the better score. We repeat this process for each possible number of teams, from k=1 to k=|V|, while keeping track of the best case.

We think this is a good approach because it allows us to minimize the second and third terms in the cost function while conceding the first term. Since the second and third terms grow exponentially and the first term grows polynomially, it is more valuable to reduce the second and third terms.

## Instructions for running the algorithm
In 'all_solvers.ipynb' jupyter notebook, there are 12 functions, each named solve(), listed under the headings "Solution #1-6" and "Other". To run our algorithm, simply define each solve() function one at a time, and then execute run_all() in main.ipynb on the test set using the currently defined solve() function. It is important to note that most of the solve() functions are very similar (naturally, because they are progressions of one another), but all of them have been preserved for the purpose of recreating results, so it is necessary to run them all.

## Final Leaderboard Position
We were ranked #25 out of 241 competing teams.
![leaderboard](https://github.com/WinsonTsangWan/CS170-project/blob/master/CS170_leaderboard_snippet.jpg)
Full leaderboard can be found here: [complete leaderboard](https://github.com/WinsonTsangWan/CS170-project/blob/master/CS%20170%20Leaderboard.pdf)
