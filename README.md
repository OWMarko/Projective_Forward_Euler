# Projective Forward Euler

> **Status :** Research Project (Archive)
> **Institution :** Université Côte d'Azur - Laboratoire J.A. Dieudonné
> **Context :** Initiation to Research Project (PIR) - Bachelor degree in Fundamental Mathematics

This repository contains the work produced during a research initiation project under the supervision of **Pr. Thomas REY**. The project focuses on two distinct numerical challenges:
1.  The analysis and implementation of the **Projective Forward Euler (PFE)** method for stiff systems.
2.  The development of a **2D Navier-Stokes solver** (Lid-Driven Cavity) using standard finite difference schemes.

### The Projective Forward Euler (PFE) Method
We studied numerical methods for **multi-scale problems** where standard explicit schemes are computationally expensive due to stiffness (spectral gap).

* **Algorithm :** Implementation of the PFE method, which combines a "micro" integrator (standard Euler) to damp fast modes and a "macro" projective step to accelerate integration along the slow manifold
* **Analysis :**
    * Derivation of **Zero-Stability** and **Absolute Stability** regions
    * Consistency analysis and order of convergence verification
* **Validation :** Tested on stiff linear ODE systems (Dahlquist test equation $y' = \lambda y$) and systems with complex eigenvalues

### 2D Navier-Stokes Solver
In parallel, we developed a fluid dynamics solver from scratch to simulate the **Lid-Driven Cavity Flow**.

* **Physics :** Unsteady Incompressible Navier-Stokes Equations
* **Methodology :**
    * **Grid:** Staggered Grid (Marker-and-Cell / MAC)
    * **Time Integration :** Chorin-Temam Projection Method (handling pressure-velocity coupling)
    * **Spatial Discretization :** Finite Differences for viscous and convective terms
* **Results :** Velocity profiles ($u, v$) obtained for Reynolds numbers $Re=100, 400, 1000$

---

### Project Note
*While the initial ambition was to apply PFE acceleration directly to the Navier-Stokes solver, time constraints prevented this final integration. However, the research objectives were fully met by :*
1.  *Conducting a deep exploration of the **PFE method** on stiff systems*
2.  *Successfully implementing a **Finite Difference solver** for a complex 2D fluid dynamics problem*

###  Tech Stack
* **Language :** Python
* **Scientific Stack :** `NumPy` (Arrays & Linear Algebra), `Matplotlib` (Visualization of stability regions and flow streamlines)

### Reference
This project relies on the following academic resources, courses, and papers:

**Primary Sources**
* **[1] Thomas Rey**, *Cours sur les Équations Différentielles et EDP*. Université Nice Côte d’Azur - M1 IM.
* **[2] Thomas Rey, R. Bailo, W. Melis, G. Samaey**, *Projective integration methods for multiscale collisional kinetic equations*. Université Nice Côte d’Azur.
* **[6] C. W. Gear and Ioannis G. Kevrekidis**, *Projective Methods for Stiff Differential Equations: Problems with Gaps in Their Eigenvalue Spectrum*, 2002.

**Numerical Analysis & ODEs**
* **[3] Florent Berthelin**, *Équations Différentielles*. Cassini Ed, 2017.
* **[4] Afeintou Sangam**, *Cours sur les Schémas Numériques des Équations Différentielles*. Université Nice Côte d’Azur - L3 Mathématiques.
* **[5] Claire Scheid**, *Cours d’Analyse Numérique 2*. Université Nice Côte d’Azur - L3 Mathématiques.
* **[9] E. Hairer, S. P. Nørsett, and G. Wanner**, *Solving Ordinary Differential Equations I: Nonstiff Problems (2nd ed.)*. Springer-Verlag, 2009.
* **[11] Jean-Pierre Demailly**, *Analyse Numérique et Équations Différentielles (4ème éd.)*. EDP Sciences, 2016.

**Fluid Dynamics & Navier-Stokes**
* **[12] Barba, Lorena A., and Forsyth, Gilbert F.** (2018), *CFD Python: the 12 steps to Navier-Stokes equations*. Journal of Open Source Education. [GitHub](https://github.com/barbagroup/cfd).
* **[14] Jacques-Louis Lions and Giovanni Prodi**, *Un théorème d’existence et unicité dans les équations de Navier-Stokes en dimension 2*. C. R. Acad. Sci., Paris, 1959.
* **[15] Alain Ciffréo, Francois Peters**, *Cours sur la mécanique des milieux continus*. Université Nice Côte d’Azur - L3 Physique.

**Advanced Research**
* **[7] Ward Melis**, *Projective Integration for Hyperbolic Conservation Laws and Multiscale Kinetic Equations*. PhD Thesis, 2017, KU Leuven.
* **[8] SIAM Journal on Scientific Computing**, *Projective Integration: A Fast and Efficient Numerical Method for Stiff Differential Equations*. 24(1): 16–40.
* **[10] Multiscale Computational Methods for Stiff Problems**, in *Computational Methods in Applied Sciences*, Vol. 4, Springer-Verlag.
* **[13] Thomas Giarrizzi, Yuran Wang**, *Non-uniqueness of Turbulent Solutions of the Navier-Stokes Equation in Dimension N = 3*. ENS PSL, 2024.


  **Authors:** SINADINOVIC Marko & BENHARRATS Nadir.
