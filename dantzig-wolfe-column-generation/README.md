# Dantzig–Wolfe Decomposition and Column Generation

This project explores large-scale optimization techniques using Dantzig–Wolfe decomposition and column generation.

The project first studies the relationship between an integer program, its LP relaxation, and a Dantzig–Wolfe reformulation. It then applies decomposition techniques to a generalized assignment problem involving jobs and machines.

## Methods

The project includes:

- Integer Programming
- LP Relaxation
- Dantzig–Wolfe Decomposition
- Convex Hull Reformulation
- Column Generation
- Pricing Subproblems
- Generalized Assignment Problem

The models were implemented in Julia using JuMP and optimization solvers.

## Part 1 – Dantzig–Wolfe Reformulation

The first part visualizes the feasible regions of an integer optimization problem and compares the original IP/LP solution with the Dantzig–Wolfe relaxation.

The Dantzig–Wolfe relaxation produced the solution:

- **DW solution:** (3, 2)
- **Objective value:** 7

while the original IP/LP optimum was:

- **IP/LP solution:** (2, 3)
- **Objective value:** 8

This illustrates how the Dantzig–Wolfe relaxation provides a bound on the original optimization problem.

## Part 2 – Column Generation

The second part considers a generalized assignment problem where five jobs must be assigned to three machines while respecting:

- Machine capacities
- Job assignment constraints
- Incompatibility constraints
- Profit maximization

The direct MIP formulation produced an optimal objective value of:

**33** 

The same problem was then reformulated using Dantzig–Wolfe decomposition.

Instead of generating every possible feasible assignment beforehand, column generation iteratively solves pricing subproblems and adds improving columns to the master problem.

The column generation algorithm converged after:

**8 iterations**

with an objective value of:

**33.0**

The explicit Dantzig–Wolfe LP relaxation also produced an objective value of **33.0**, confirming that both approaches solve the same reformulated LP.

