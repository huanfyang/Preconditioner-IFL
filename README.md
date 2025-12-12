# A Fast Matrix-Free Preconditioning Method for 3D Nonlocal BVPs with Integral Fractional Laplacian on Arbitrary Bounded Domains

This repository presents a finite difference method and its fast algorithms for three-dimensional nonlocal boundary-value problems involving the integral fractional Laplacian with variable diffusion coefficients.

## Overview

A simple and easy-to-implement fractional central difference (FCD) method is used to discretize the nonlocal operator, resulting in a linear system with a multilevel Toeplitz-plus-diagonal structure. Due to the non-constant diagonal in the discretization matrix, the standard FFT-based circulant preconditioner is not directly applicable.

To address this issue, we construct two matrix-free preconditioners by combining the approximate inverse multilevel circulant matrices row-by-row. Both preconditioners can be implemented using FFT with **𝒪(n³ log n)** computational complexity and **𝒪(n³)** memory usage, where *n* is the number of grid points per direction.

Preconditioning techniques combined with fast BiCG and BiCGSTAB solvers significantly reduce both the iteration count and CPU time. A notable advantage of the proposed method is its straightforward extension to arbitrary three-dimensional irregular domains through a fictitious domain scheme.

Extensive numerical experiments are performed on complex geometries including spherical, torus, tanglecube, and molecular surfaces, demonstrating the effectiveness and robustness of the proposed algorithms.
