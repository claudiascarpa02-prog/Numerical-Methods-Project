# MATLAB Built-in Solvers: bvp4c vs bvp5c
> **A comparative study on numerical solutions for Boundary Value Problems (BVPs)**

[![MATLAB](https://img.shields.io/badge/MATLAB-R2024-orange.svg)](https://www.mathworks.com/products/matlab.html)
[![Topic](https://img.shields.io/badge/Topic-Numerical_Methods-blue.svg)]()

This project explores the theoretical foundations and practical applications of collocation-based techniques for solving Boundary Value Problems. The research focuses on a performance comparison between MATLAB's `bvp4c` and `bvp5c` solvers.

---

## Project Overview
We explore how the order of Lobatto IIIa formulas affects solution accuracy and stability:
-bvp4c: Lobatto IIIa, 4th order
-bvp5c: Lobatto IIIa, 5th order

Key aspects analyzed include Residual control, Computational efficiency and Sensitivity to initial guesses

## Repository Structure
```text
├── code/
│   ├── examples/     # Standard test cases for solver verification
│   ├── exercises/    # Complex applications (Bratu's problem, Gas dynamics,...)
│   └── bvp_app          # Interactive environment for performance exploration
├── docs/
│   ├── Solving BVP for ODE in MATLAB with bvp4c.pdf  # Reference paper for project methodology and examples
│   └── report.pdf   # Full technical report
└── README.md
```

## Implementation Details
The project is structured to ensure modularity:
* **Problem Re-formulation**: Each example/exercise is implemented as a standalone MATLAB function, re-formulating the mathematical problems described in the reference paper.
* **Main Controller**: `bvp_app.m` acts as the central script, calling these specific problem formulations to execute the `bvp4c` and `bvp5c` solvers and compare their results.
* ** Advanced Techniques**: For singular or three-point BVPs, strategies like Continuation and Separation are applied

## Solvers Comparison
| Feature | bvp4c | bvp5c |
| :--- | :--- | :--- |
| **Formula** | Lobatto IIIa (4th order) | Lobatto IIIa (5th order) |
| **Robustness** | Higher (better for poor initial guesses) | Lower (sensitive to initial guess) |
| **Accuracy** | Standard | High (efficient for smooth solutions) |
| **Cost** | Lower | Higher |

## Getting Started
1. **Clone the repository**:
   ```bash
   git clone [https://github.com/ClaudiaScarpa/Numerical-Methods-Project.git](https://github.com/ClaudiaScarpa/Numerical-Methods-Project.git)

2. **Open MATLAB** and navigate to the code/ folder.
3. **Run the bvp_app** to generate comparison plots,
3. **Check the Report (docs/report.pdf)** for a detailed discussion about the theoretical backgrounds, and analysis of some case studies.
---
## Key Findings
Our analysis confirms that while both solvers share the same underlying methodology, bvp4c is generally preferable for its computational reliability and robustness. In contrast, bvp5c becomes more advantageous when high-level accuracy is required and the solution is sufficiently smooth.
---
## References

1. MATLAB Documentation: [bvp4c](https://www.mathworks.com/help/matlab/ref/bvp4c.html) & [bvp5c](https://www.mathworks.com/help/matlab/ref/bvp5c.html)

2. Shampine, L.F., M.W. Reichelt, and J. Kierzenka. Solving Boundary Value Problems for Ordinary Differential Equations in MATLAB with bvp4c. MATLAB File Exchange, 2000.
3. A. Spielauer and E.B. Weinmuller. ¨ Numerical solution of boundary value problems in ordinary differential equations with time and space singularities. Institute for Analysis and Scientific Computing, Vienna, University of Technology, 2015.

