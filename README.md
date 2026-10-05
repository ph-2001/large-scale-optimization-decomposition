# Stochastic Optimization Using Decomposition Methods

This project explores two-stage stochastic optimization for capacity planning under uncertain demand.

The goal is to decide which suppliers to use and how much capacity to reserve before demand is known, while minimizing the expected total cost. Once a demand scenario is realized, the reserved capacity is allocated to customers and unmet demand may be penalized. :chatgpt-content-reference{index="0"}

## Methods

The project includes:

- Extensive-form stochastic optimization
- Benders Decomposition
- Benders feasibility cuts
- Single-cut and multi-cut Benders
- Progressive Hedging
- Scenario-based optimization

The Benders implementation was developed in Julia using JuMP and HiGHS. :chatgpt-content-reference{index="1"}

Progressive Hedging was implemented in Julia using JuMP and Gurobi. :chatgpt-content-reference{index="2"}

## Results

The extensive-form model produced an optimal objective value of **11,922.8**. :chatgpt-content-reference{index="3"}

The multi-cut Benders approach converged in only **7 iterations**, while the single-cut version required more than **100 iterations**, showing a substantial improvement in convergence speed for this problem. :chatgpt-content-reference{index="4"}

The Progressive Hedging algorithm converged after **57 iterations** with a final residual of approximately **5.87 × 10⁻³**. :chatgpt-content-reference{index="5"}
