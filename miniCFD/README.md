# MiniCFD
## A simple finite volume CFD solver for the Elemnt Multiphysics Framework.

### Overview

- Initially the solver will be implemented for 2D problems, with structured meshes. Unstructured meshes and 3D problems will be added later.
- The solver will be implemented using the finite volume method, with a focus on simplicity and ease of use. The solver will be designed to be easily extensible, so that new features can be added in the future.
- The solver will be implemented in C++, with a focus on performance and scalability. The solver will be designed to utilize the metal performance shaders for GPU acceleration, and will be optimized for use on Apple Silicon devices.


### Governing Equations

For the initial implementation, the solver will be designed to solve the incompressible Navier-Stokes equations, which govern the flow of incompressible fluids. The equations are given by: $$ \del \cdot \mathbf{u} = 0 $$ $$ \frac{\partial \mathbf{u}}{\partial t} + (\mathbf{u} \cdot \nabla) \mathbf{u} = -\nabla p + \nu \nabla^2 \mathbf{u} + \mathbf{f} $$ where $\mathbf{u}$ is the velocity field, $p$ is the pressure field, $\nu$ is the kinematic viscosity, and $\mathbf{f}$ is the body force per unit mass.


### Roadmap

1. Scalar Diffusion Solver: before velocity and pressure, build scalar diffusion code on a structured grid: $$ -\del^2 \phi = f$$
 - [ ] mesh indexing
 - [ ] cell-centered storage
 - [ ] sparse matrix assembly
 - [ ] Dirichlet and Neumann boundary conditions
 - [ ] iterative solvers (e.g. Jacobi, Gauss-Seidel, Conjugate Gradient)
2. Pressure Poisson Solver: build a solver for the pressure Poisson equation