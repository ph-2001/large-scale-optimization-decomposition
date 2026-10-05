# Large-Scale Optimization Using Decomposition

This repository contains two projects from the DTU course **42136 – Large Scale Optimization using Decomposition**.

The projects explore decomposition methods for solving large and structured optimization problems. The implementations are written mainly in **Julia** using **JuMP** and optimization solvers such as **HiGHS, GLPK, and Gurobi**.

## Project 1 – Benders Decomposition and Progressive Hedging

The first project considers a two-stage stochastic capacity planning problem under uncertain demand.

The main decision is how much capacity to reserve from different suppliers before future demand is known. Once a demand scenario is realized, the reserved capacity is allocated to clients while balancing transportation costs and penalties for unmet demand.

The project includes:

- Two-stage stochastic optimization
- Benders Decomposition
- Benders optimality cuts
- Benders feasibility cuts
- Single-cut vs. multi-cut Benders
- Progressive Hedging
- Scenario-based optimization

The extensive-form model obtained an optimal objective value of **11,922.8**.

The multi-cut Benders implementation converged in only **7 iterations**, while the single-cut approach required more than **100 iterations**, showing a substantial improvement in convergence for this problem. 

Progressive Hedging was also implemented to decompose the stochastic problem into scenario-specific subproblems. The algorithm converged after **57 iterations** with a final residual of approximately **5.87 × 10⁻³**. 

## Project 2 – Dantzig–Wolfe Decomposition and Column Generation

The second project focuses on Dantzig–Wolfe decomposition and column generation.

The first part studies the relationship between an integer program, its LP relaxation, and a Dantzig–Wolfe reformulation.

The second part applies column generation to a generalized assignment problem where jobs must be assigned to machines while respecting capacity and incompatibility constraints.

The project includes:

- Integer Programming
- LP Relaxation
- Dantzig–Wolfe Decomposition
- Convex hull reformulation
- Restricted master problems
- Pricing subproblems
- Column Generation
- Generalized Assignment Problem

The direct MIP formulation produced an optimal objective value of **33**.
The column generation algorithm converged after **8 iterations** and obtained the same objective value of **33.0**. 

An explicit Dantzig–Wolfe LP formulation also produced an objective value of **33.0**, confirming the equivalence between explicitly enumerating all columns and generating only the necessary columns iteratively.
