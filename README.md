# F# Mutable Variable Swap Bug

This repository demonstrates a common bug in F# related to the misuse of mutable variables within functions. The `swap` function attempts to swap the values of two mutable variables, but due to the way F# handles value parameters, it fails to modify the original variables.

## Bug Description

The `bug.fs` file contains a function called `swap` that attempts to swap the values of two mutable variables (`x` and `y`). However, because F# passes arguments by value, the function creates copies of the input variables.  The modifications made inside the function only affect these copies, leaving the original variables unchanged.

## Solution

The solution is to use the `byref` keyword to pass the variables by reference. The `bugSolution.fs` file shows the corrected version. By passing the variables by reference, the function modifies the original variables directly.

## How to run

1.  Make sure you have the .NET SDK and F# installed.
2.  Clone this repository.
3.  Open the solution in your favorite F# IDE or use the F# interactive compiler (fsi) to run the code in `bug.fs` and `bugSolution.fs` and observe the difference in output.