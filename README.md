# Projective Forward Euler (PFE) - Python Implementation

> **Context:** Research Internship (Bs) at Laboratoire J.A.D.  
> **Topic:** Numerical Analysis of Stiff Differential Equations & Multi-scale Simulation.

## The Problem : Stiff Equations

This project addresses a classic problem in numerical analysis: **Stiffness**.

In many physical or biological systems (like chemical reactions), you have processes happening at very different speeds simultaneously.
* **Fast dynamics:** Variables that change instantly (e.g., rapid chemical bonding).
* **Slow dynamics:** Variables that evolve over a long period.

Standard solvers (like `ode45` or standard Euler) are forced to take incredibly small time steps to capture the "fast" stuff, even if we only care about the "slow" evolution. This makes simulations painfully slow.

## The Solution : Projective Integration

This repository implements the **Projective Forward Euler (PFE)** method. The goal is to speed up the simulation by skipping the expensive computation of fast dynamics once they have decayed.

**How the algorithm works:**
1.  **Inner Integrator :** We take a few small steps ($k$ steps of size $\delta t$) using a standard explicit method to dampen the fast modes.
2.  **Projection (Extrapolation) :** We use the last two points to estimate the derivative of the slow variables.
3.  **Macro Step :** We project the solution far into the future (step $M \gg \delta t$) linearly.

This effectively allows us to "jump" over time, maintaining stability without computing every single micro-second.

## Implementation Details

The code is written in pure Python using `NumPy` for vectorized operations, making the mathematical translation of the algorithm straightforward and readable.

## Results & Visualization

I benchmarked the PFE method against a standard explicit Euler scheme.
The implementation demonstrates that for a stiff parameter $\epsilon = 10^{-3}$, the Projective method remains stable with a time step significantly larger than the stability limit of the standard solver.
