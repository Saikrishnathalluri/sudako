# Milestone-2: SUDOKU
for see the output :[click_here](http://127.0.0.1:5500/sudhir/index.html)

## Problem Statement

[Sudoku](http://en.wikipedia.org/wiki/Sudoku) is a logic-based, combinatorial number-placement puzzle. The objective is to fill a 9×9 grid with digits so that each column, each row, and each of the nine 3×3 sub-grids that compose the grid (also called "boxes") contains the digits from 1 to 9.

Generally, a puzzle provides a partial solution so that some squares already have numbers. To solve the puzzle, we need to fill in the unsolved squares, as demonstrated in Figure 1.

By the end of this challenge we'll have a fully functioning Sudoku solver that runs from the `command line`.  We'll be presented with 9x9 unsolved Sudoku puzzle grid. The puzzles grid can be found in the file `sudoku_puzzles.txt`.

Sudoku Solver is basically your code that takes your input and produces output mathematically

<b>Input</b>: format Space separated given numbers in the grid ( 0 for empty place ) in `sudoku_puzzles.txt`

<b>Output</b>: format 9x9 sudoku grid

A complete solution to this challenge take Input 9x9 and produce output grid 9x9

## Approach
The naive approach is to generate all possible configurations of numbers from 1 to 9 to fill the empty cells. 
Try every configuration one by one until the correct configuration is found, i.e. for every unassigned position fill the position with a number from 1 to 9. 
After filling all the unassigned position check if the matrix is safe or not. If safe print else recurs for other cases.

## Algorithm
1.Create a function that checks if the given matrix is valid sudoku or not. Keep Hashmap for the row, column and boxes. If any number has a frequency greater than 1 in the hashMap return false else return true;

2.Create a recursive function that takes a grid and the current row and column index.

3.Check some base cases. If the index is at the end of the matrix, i.e. i=N-1 and j=N then check if the grid is safe or not, if safe print the grid and return true else return false. The other base case is when the value of column is N, i.e j = N, then move to next row, i.e. i++ and j = 0.

4.if the current index is not assigned then fill the element from 1 to 9 and recur for all 9 cases with the index of next element, i.e. i, j+1. if the recursive call returns true then break the loop and return true.

5.if the current index is assigned then call the recursive function with index of next element, i.e. i, j+1