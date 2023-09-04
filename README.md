## Introduction

This is a puzzle game consiting of a 2d grid with obstacle nodes and normal nodes. The player has to find a path in the grid that visits all the normal nodes essentially forming a hamiltonian path. There is one source node, multiple end nodes and one of them will hightlighted. The difficulty increases with grid size. The grid dimension can be at most 12x12 which is really difficult to solve. In case the player is stuck there is an autosolve button for some clarity. And of course there is a dark mode.

All puzzles are randomly generated.

This is the game menu in light and dark mode

<img src="https://github.com/renzhamin/a-way-out/assets/57265942/300d2d47-6c9c-43cc-af4d-ca7f6ba9216b" height="400px" />


## Sample Puzzle

This is how a 5x5 puzzle and its solution looks like

<img src="https://github.com/renzhamin/a-way-out/assets/57265942/e132a97d-89d0-4782-a835-4c9d41eb5670" height="400px" />

Here the orange node is the source node. The nodes are traversed by dragging with left mouse button and undoing is done by clicking right mouse button in any cell.


A sample puzzle with max difficulty

<img src="https://github.com/renzhamin/a-way-out/assets/57265942/cda902f5-76b7-45cb-8b6d-e27a5b4912b2" height="400px" />

Here, the game is in dark mode.





## Level Selection

1. Random : Generate a puzzle with random difficulty (random grid size)
2. Level : Increase difficulty as the level goes up.
3. Dimension : The dimension of the 2D grid is specified.

   <img src="https://github.com/renzhamin/a-way-out/assets/57265942/14ba3791-c655-47c1-94ec-adc67424aa3a" height="400px"/>


## Mechanism of random puzzle generation

The `generateGrid(n,m)` function generates a random grid of nxm. 

1. First a source node is chosen randomly.
2. Then a valid adjacent node in any of the 4 direction is chosen randomly and .
3. Step 2 is repeated until we can't traverse to a node in any direction.
4. The nodes that were not traversed become obstacle nodes and the rest becomes normal nodes.

`assignGoodGrid` function runs this algorithm 1000 times and choses the best grid. A grid is good if its obstacle nodes are scattered throughout the grid. For each grid a badness factor is calculated which becomes a large value if the obstacle nodes are grouped together. The grid with the least badness factor is chosen.


## Installation & Development

1. Install g++ and sfml for your system.
2. Clone this repo

```sh
git clone https://github.com/renzhamin/a-way-out
cd a-way-out
```

3. Build and run the game

```sh
make
./Program
```

