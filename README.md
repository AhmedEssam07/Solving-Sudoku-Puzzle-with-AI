# Solve Sudoku with AI

## 1.Introduction
In this blog we will concentrate on two main concepts, constraint propagation and search. To learn these concepts, we will build an AI agent that will solve any sudoku puzzle. As you know sudoku puzzle consists of 9 x 9 square with each row, column and 3 x 3 subsquares containing the numbers from 1 to 9 appearing exactly once. Here is an example of suduku puzzle and the corresponding solution. 

![exampel image](https://github.com/mohandesosama/Solving-Sudoku-Puzzle-with-AI/blob/master/images/sudo-ku-puzzle-example.png)

We will build an agent with python that will solve any sudoku. It is abased on Peter Norvig [[blog]](http://norvig.com/sudoku.html), 

## 2.Solving a sudoku
### What is a Sudoku?
[Sudoku](https://en.wikipedia.org/wiki/Sudoku) is one of the world's most popular puzzles. It consists of a 9x9 grid, and the objective is to fill the grid with digits in such a way that each row, each column, and each of the 9 principal 3x3 subsquares contains all of the digits from 1 to 9. The detailed rules can be found, for example, [here](http://www.conceptispuzzles.com/?uri=puzzle/sudoku/rules). The puzzle is given as a partially completed grid, and the goal is to fill in the missing numbers. Below is an example of such a grid.

<img src="./images/an_example_of_sudoku_grid.png" alt="sudoku puzzle" width="400" align="middle"/>

### Goals of this project
The main goal of this project is to build an intelligent agent that will solve every sudoku while introducing you to two powerful techniques that are used throughout the field of AI:

#### 1 Constraint Propagation
When trying to solve a problem, you'll find that there are some local constraints to each square. These constraints help you narrow the possibilities for the answer, which can be very helpful. We will learn to extract the maximum information out of these constraints in order to get closer to our solution. Additionally, you'll see how we can repeatedly apply simple constraints to iteratively narrow the search space of possible solutions. Constraint propagation can be used to solve a variety of problems such as calendar scheduling, and cryptographic puzzles.
#### 2 Search
In the process of problem solving, we may get to the point where two or more possibilities are available. What do we do? What if we branch out and consider both of them? Maybe one of them will lead us to a position in which three or more possibilities are available. Then, we can branch out again. At the end, we can create a whole tree of possibilities and find ways to traverse the tree until we find our solution. This is an example of how search can be used.
These ideas may seem simple and they're actually intended to be! Through this lesson you'll see how AI is really composed of very simple ideas that can be put together to solve complex problems. Throughout this lesson, we challenge you to think of how you can apply these ideas to build AI agents to solve other puzzles and problems in your world!

## 3. Setting up the Board
### Sudoku: Solution
The solution of sudoku should follow the following rules:

* If a box has a value, then all the boxes in the same row, same column, or same 3x3 square cannot have that same value.
* If there is only one allowed value for a given box in a row, column, or 3x3 square, then the box is assigned that value.

The puzzle is given as a partially completed grid, and the goal is to fill in the missing numbers. Below is an example of such a grid.

<img src="./images/sudoku-easy-solution.png" width="400"/>

### Naming Conventions
#### Rows and Columns
Since we're writing an agent to solve the Sudoku puzzle, let's start by labelling rows and columns.

* The rows will be labelled by the letters A, B, C, D, E, F, G, H, I.
* The columns will be labelled by the numbers 1, 2, 3, 4, 5, 6, 7, 8, 9. Here we can see the unsolved and solved puzzles with the labels for the rows and columns.
* The 3x3 squares won't be labelled, but in the diagram, they can be seen with alternating colors of grey and white.

#### Boxes, Units and Peers
And let's start naming the important elements created by these rows and columns that are relevant to solving a Sudoku:

* The individual squares at the intersection of rows and columns will be called `boxes`. These boxes will have labels 'A1', 'A2', ..., 'I9'.
* The complete rows, columns, and 3x3 squares, will be called `units`. Thus, each unit is a set of 9 boxes, and there are 27 units in total.
* For a particular box (such as 'A1'), its `peers` will be all other boxes that belong to a common unit (namely, those that belong to the same row, column, or 3x3 square).

Let's see an example. In the grids below, the set of highlighted boxes represent units. Each grid shows a different peer of the box at E3.

<img src="./images/peers.png"/>

Let's test your understanding! For any box, how many peers are there?
Answer (20)

## 4.Encoding the Board
                                         
## References
Peter Norvig, Solve every sudoku puzzle [[blog]](http://norvig.com/sudoku.html)
