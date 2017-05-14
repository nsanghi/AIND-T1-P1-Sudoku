# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: This strategy is implemented in function `naked_twins`
1. for `unit` in `all_units`:
   1. filter the boxes in a unit which meet the condition of naked twins.
   2. go over all other boxes in unit and remove the two possible assignments from their list of possible values in those boxes
   3. return the modified sudoku grid
2. In function `reduce_puzzle`, we used to call two reduction strategies, a) `eliminate` to find a box with assigned value(i.e. box having only one possible choice.
b) `only_choice` to assign a value to a box in a unit if that value is a possible value in only one box in that unit.
 
   Now we also call `naked_twins` in this code block as a 3rd reduction strategy.
        

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: I added the two diagonal units to the list of units which enables the constraint checking when we go over the units in `eliminate` and `naked_twins`. The Diagonal units were built using code like:
```
diagonal_1 = [[r+c for r,c in zip(rows,cols)]]
diagonal_2 = [[r+c for r,c in zip(reversed(rows),cols)]]
```
### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solution.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Submission
Before submitting your solution to a reviewer, you are required to submit your project to Udacity's Project Assistant, which will provide some initial feedback.  

The setup is simple.  If you have not installed the client tool already, then you may do so with the command `pip install udacity-pa`.  

To submit your code to the project assistant, run `udacity submit` from within the top-level directory of this project.  You will be prompted for a username and password.  If you login using google or facebook, visit [this link](https://project-assistant.udacity.com/auth_tokens/jwt_login for alternate login instructions.

This process will create a zipfile in your top-level directory named sudoku-<id>.zip.  This is the file that you should submit to the Udacity reviews system.

