# AM5630: Introduction to Computational Fluid Dynamics

## 2D Channel Flow (Plane-Poiseuille Flow)
### 1. Problem Description

Consider a two-dimensional channel of length `L` and height `H`.

An incompressible fluid enters the channel through the inlet with a uniform velocity `U`. The objective is to numerically simulate the flow development inside the channel using a finite difference method and study the velocity and pressure distributions.

### 2. Problem Statement

Determine the fluid flow pattern and pressure distribution along the channel using any finite difference method covered in the AM5630 course.

The governing equations must be expressed in non-dimensional form with appropriate initial and boundary conditions.

The following objectives must be addressed:

1. Plot the streamlines of the flow.
2. Plot the velocity magnitude distribution throughout the channel.
3. Plot the pressure distribution.
4. Plot the `u`-velocity profiles at `x = 1, 2, ..., 10`, considering all values of `y` at intervals of 1 unit.
5. Determine the hydrodynamic entry length, i.e., the location where the flow becomes fully developed.
6. Compare the numerical results with the analytical solution for Plane-Poiseuille flow available in standard Advanced Fluid Mechanics textbooks.

### 3. Assumptions

- The fluid is incompressible.
- The flow is steady-state and two-dimensional.
- The Reynolds number is `Re = 100`.

### 4. Computational Domain

| Parameter | Value |
|---|---:|
| Channel length (L) | 10 |
| Channel height (H) | 1 |
| Reynolds number (Re) | 100 |
| Number of grid points in x-direction (Nx) | 101 |
| Number of grid points in y-direction (Ny) | 41 |
| Time step (dt) | 0.001 |
| Maximum iterations | 50,000 |

### 5. Governing Equations

The non-dimensional governing equations for incompressible flow are:

**X-Momentum Equation**

$$
\frac{\partial u}{\partial t}+u\frac{\partial u}{\partial x}+v\frac{\partial u}{\partial y}=-\frac{\partial p}{\partial x}+\frac{1}{Re}\left(\frac{\partial^2u}{\partial x^2}+\frac{\partial^2u}{\partial y^2}\right)
$$

**Y-Momentum Equation**

$$
\frac{\partial v}{\partial t}+u\frac{\partial v}{\partial x}+v\frac{\partial v}{\partial y}=-\frac{\partial p}{\partial y}+\frac{1}{Re}\left(\frac{\partial^2v}{\partial x^2}+\frac{\partial^2v}{\partial y^2}\right)
$$

**Continuity Equation**

$$
\frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}=0
$$

### 6. Initial and Boundary Conditions

**Initial Conditions**

$$
u(x,y,0)=0,\qquad v(x,y,0)=0
$$

**Inlet (x = 0)**

$$
u(0,y)=1,\qquad v(0,y)=0
$$

**Channel Walls (y = 0, 1)**

$$
u(x,0)=u(x,1)=0
$$

$$
v(x,0)=v(x,1)=0
$$

**Outlet (x = L)**

$$
\frac{\partial u}{\partial x}=0,\qquad
\frac{\partial v}{\partial x}=0
$$

### 7. Numerical Method

The problem is solved using the **Marker-and-Cell (MAC) method**, employing a finite difference discretization of the incompressible Navier–Stokes equations.

The numerical procedure consists of:

1. Initialization of velocity and pressure fields.
2. Computation of intermediate velocities using the momentum equations.
3. Solution of the pressure Poisson equation.
4. Correction of velocity fields to satisfy the continuity equation.
5. Application of boundary conditions.
6. Iteration until the solution reaches steady state.

### 8. Expected Results

The numerical simulation should produce the following results:

- Streamline plot illustrating the flow development.
- Contour plot of velocity magnitude.
- Pressure distribution along the channel.
- Axial velocity profiles at different streamwise locations.
- Estimation of the hydrodynamic entry length.
- Comparison between numerical and analytical Plane-Poiseuille velocity profiles.

### 9. Analytical Reference: Plane-Poiseuille Flow

For fully developed, steady, incompressible, and unidirectional flow between two parallel stationary plates, the analytical velocity distribution is parabolic:

$$
u(y)=\frac{1}{2\mu}
\left(-\frac{dp}{dx}\right)
(Hy-y^2)
$$

The transverse velocity is zero:

$$
v(y)=0
$$

The numerical solution is compared against this analytical profile to assess the accuracy of the computational method.

---

**Course:** AM5630 – Introduction to Computational Fluid Dynamics

**Assignment:** Computer Assignment 3

**Problem:** 2D Channel Flow (Plane-Poiseuille Flow)
