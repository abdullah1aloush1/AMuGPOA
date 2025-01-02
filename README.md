# Angle-Based Multi-Goal Ordering And Path-Planning Using An Improved A* Algorithm (AMuGOPIA)

## Overview

The repository for Angle-Based Multi-Goal Ordering And Path-Planning Using An Improved A* Algorithm (AMuGOPIA). A scientific journal paper submitted to Robotics and Autonomous Systems in the fields of Path-Planning, Multi-Goal Pathfinding, A-Star Search Algorithm, Robotic Navigation and Autonomous Mobile Robots.

- **Authors:** [Abdullah Allus](https://scholar.google.com/citations?user=rDlVCVUAAAAJ&hl=en), [Mustafa Unel](https://scholar.google.com/citations?hl=en&user=h4lFct0AAAAJ&view_op=list_works).
- **Maintainer:** [Abdullah Allus](https://github.com/abdullah1aloush1).

## Abstract

In the field of autonomous mobile robotics, the demand for highly efficient path-planning algorithms is crucial. Among the various path-planning tasks and challenges, multi-goal path planning stands out as a particularly complex problem, where the objective is to determine the most efficient path for a robot to visit multiple goal nodes. In this paper, we introduce a novel ordering algorithm designed to optimize the sequence in which the goal nodes are visited. The ordering is based on a one-distance-two-angles ordering paradigm, which reduces the dependency on distances as deciding factors and incorporates more angles to gather the necessary information, thereby reducing the computational complexity of the overall ordering procedure. The backbone of the algorithm is an improved version of the A* search algorithm that we developed to further reduce the distance cost of the original A* algorithm by solving some internal issues caused by the nature of the algorithm when dealing with grid-based environments. Extensive experiments were conducted to demonstrate the computational efficiency and cost-effectiveness of our proposed algorithm. The scalability and reproducibility of the proposed ordering algorithm and the improved A* were validated by testing them on various publicly available maps in numerous different scenarios. We also performed comprehensive comparisons with existing state-of-the-art algorithms to evaluate the performance. The conducted experiments report that our proposed algorithm consistently outperformed other algorithms in numerous scenarios, underscoring its reliability and potential to match or exceed the performance of current state-of-the-art methods in the domain of multi-goal path planning. The Python code, map and other resources of our proposed algorithms are available at https://github.com/abdullah1aloush1/AMuGOPIA.

## AMuGOPIA's Methodology

AMuGOPIA is a set of several algorithms integrated together. The integrated framework takes a top-view 2D image map file of an autonomous mobile robot's workspace as input. The input map should contain only black and white coloured areas, where white coloured areas represent navigable passages for the robot, while black areas represent blocked passages that the robot can not navigate through (obstacles).

AMuGOPIA works mainly on finding a near-optimal visiting configuration (order) to visit the provided goal nodes. Then, it connects the ordered goal nodes by navigable path sections providing sampled path coordinates along the whole path.

The framework finally outputs a list of the coordinates for the overall path and plots it as a figure.

### Work Flow:


- Pre-Processing Module <br>
The framework processes the input map of the workspace. This process involves generating grid equidistant nodes, defining neighbourhood relations to form an efficient neighbourhood graph, establishing cost definitions, and detecting obstacles. This structured foundation is crucial for the effectiveness of the subsequent modules.

- Ordering Module <br>
This module uses the novel ordering algorithm utilising geometrical information obtained by the introduced angles and the one-distance-two-angle paradigm to dynamically order the goal nodes to minimize overall cost and time complexity taking local and global information into account.

- Improved A* Module <br>
This module utilises the improved version of the A* algorithm used to find the shortest path between two nodes. The improvements include integrating the pre-processed map, ensuring obstacle avoidance, managing cost considerations, and post-pruning the generated path. These modifications optimize the A* algorithm for its application in the ordering algorithm.


![Algorithm Flowchart](figures/GraphicalAbstract.png)

