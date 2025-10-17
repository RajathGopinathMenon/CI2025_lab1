# CI2025_lab1

Knapsack Solver

This solver uses a Hill Climbing method, which is a simple search strategy that tries to find the best solution by making small, locally optimal improvements.

The Process

Start Feasible: The algorithm first creates an empty solution and uses a Repair Tool (make_valid) to fill it with items until it becomes a legal starting point (no knapsack is overloaded, and no item is in two places).

Tweak and Test: In each step, the solver takes the current best solution and creates a neighbor using the Tweak Tool (tweak). This tool works by randomly trying to add one unassigned item to an available knapsack.

Acceptance: The solver calculates the Fitness (total value) of the new solution. If the new solution is illegal (e.g., the added item causes an overload), its fitness is terrible.

The core rule is: The move is only accepted if the new solution's total value is strictly higher than the current solution's value. We never accept worse or equal moves.

Local Optimum: The process repeats, always improving the solution's value, until it can no longer find any simple "add item" move that increases the total value. At this point, the algorithm stops, having found a local optimum.