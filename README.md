# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A:  In the naked twin strategy, if there are two boxes with only two digits and both the boxes contain the same two digits then we know that one of the two boxes will contain one digit and the other box the second digit. eg one box contains 45 and other contains 54 then we don't know which one has a 4 and which one has a 5, but we know one thing for sure — the values 4 and 5 are locked in those two boxes, so no other box in their same unit can contain the values 4 or 5. Therefore we can safely remove these digits from the other boxes in the same unit. 
The two digits are constrained to the two boxes and when this constraint is propagated to the remaining boxes it   eliminates the digits from the remaining boxes. This makes it faster for us to deduce the possible values in the boxes thereby making the sudoku reach a solution or not much faster.
 

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: Constraint Propagation is all about using local constraints in a space (in the case of Sudoku, the constraints of each square) to dramatically reduce the search space. As we enforce each constraint, we see how it introduces new constraints for other parts of the board that can help us further reduce the number of possibilities
Diagonal Sudoku has additional constraints such that the left and right diagonals should have only one occurence of all digits from 1 to 9. Thus the units now contain two additional sets of boxes and peers of the 'greyed out '
square units have additional units to look for constraints.Thus with diagonal sudoku we check if only_choice and eliminate can be applied to the diagonal sqaures  and propagate this constraint to the remaining cells. 

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.
