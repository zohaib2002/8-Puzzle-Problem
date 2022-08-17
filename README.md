# 8 Puzzle Problem

The 8 puzzle problem involves a 3X3 grid with the numbers 0 to 8 and an empty slot all arranged in random order. The objective is to move the empty slot in a specific sequence to get all the numbers in a specified order.

![n-puzzle](https://repository-images.githubusercontent.com/479162603/40499170-5c6a-4d00-a928-88784ebc4d3e)

##  Manhattan distance

The Manhattan distance is the sum of the displacement of each tile from its preferred position. For example in the above image the Manhattan distance would be: 4 + 4 + 2 + 0 + 2 + 4 + 2 + 3 = 21

## Solution using Informed Search

In this approach we move the empty slot to next possible locations and find the Manhattan distances of the new configurations. The configuration having the least Manhattan distance is explored further. This is repeated until we reach the desired state.

## Implementation in Python

In the code provided, we have used several variables and functions.
- The `initial_state` stores the initial state of the grid where the empty slot is represented by 0.
- The `goal_state` stores the final / required state of the grid.
- The `state_history` stores all the states that are visited / explored to avoid revisiting them.
- The `manhattan()` function returns the Manhattan distance of a state passed as argument.
- `moves()` returns a list of all possible moves that can be performed for the given location of the empty slot. This is a list of integers where each value represents a move:
	- 0: up
	- 1: right
	- 2: down
	- 3: left
- `explore()` function explores a move passed as argument and returns the Manhattan distance of the state it leads to. It return infinity (9999) if it leads to a previously explored state.
- The `execute()` function executes a move passed as argument and makes changes to the initial change.
- The `__main()__` functions finds the best move and executes it until the `initial_state` is the same as the `goal_state`.

