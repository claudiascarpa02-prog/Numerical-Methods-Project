# MATLAB Built-in Solvers: bvp4c vs bvp5c
> **A comparative study on numerical solutions for Boundary Value Problems (BVPs)**

[![MATLAB](https://img.shields.io/badge/MATLAB-R2024-orange.svg)](https://www.mathworks.com/products/matlab.html)
[![Topic](https://img.shields.io/badge/Topic-Numerical_Methods-blue.svg)]()

This project explores the theoretical foundations and practical applications of collocation-based techniques for solving Boundary Value Problems. The research focuses on a performance comparison between MATLAB's `bvp4c` and `bvp5c` solvers.

---

## Project Overview
The study investigates how different orders of Lobatto IIIa formulas affect the accuracy and stability of numerical solutions. We analyze:
* **Lobatto IIIa (4th order)** implemented in `bvp4c`.
* **Lobatto IIIa (5th order)** implemented in `bvp5c`.

Key areas of focus include **residual control**, **computational efficiency**, and **sensitivity to initial guesses**.

## Repository Structure
```text
├── code/
│   ├── examples/     # Standard test cases for solver verification
│   ├── exercises/    # Complex applications (Bratu's problem, Gas dynamics,...)
│   └── GUI/          # Interactive environment for performance exploration
├── docs/
│   ├── Solving BVP for ODE in MATLAB with bvp4c.pdf  # Reference paper for project methodology and examples
│   └── report.pdf   # Full technical report
└── README.md
```

## Implementation Details
The project is structured to ensure modularity:
* **Problem Re-formulation**: All examples and exercises are implemented as standalone functions, re-formulating the mathematical problems described in the reference paper.
* **Main Controller**: The `bvp_app.m` script (or notebook) acts as the central controller, calling these specific problem formulations to execute the `bvp4c` and `bvp5c` solvers and compare their results.
* **Specialized Techniques**: For specific complex cases—such for example those with singularities or three point bvp—the project employs advanced strategies like Continuation, Separation, etc...

## Solvers Comparison
| Feature | bvp4c | bvp5c |
| :--- | :--- | :--- |
| **Formula** | Lobatto IIIa (4th order) | Lobatto IIIa (5th order) |
| **Robustness** | Higher (better for poor initial guesses) | Lower (sensitive to initial guess) |
| **Accuracy** | Standard | High (efficient for smooth solutions) |
| **Cost** | Lower per iteration | Higher per iteration |

## Getting Started
1. **Clone the repository**:
   ```bash
   git clone [https://github.com/ClaudiaScarpa/Numerical-Methods-Project.git](https://github.com/ClaudiaScarpa/Numerical-Methods-Project.git)

2. **Run MATLAB**: Open the code/ folder and execute the scripts to generate the comparison plots.

3. **Check the Report**: For a deep dive into the mathematical proofs and results, refer to the PDF Report.
---
## Key Findings
Our analysis confirms that while both solvers share the same underlying methodology, bvp4c is generally preferable for its computational reliability and robustness. In contrast, bvp5c becomes more advantageous when high-level accuracy is required and the solution is sufficiently smooth.
