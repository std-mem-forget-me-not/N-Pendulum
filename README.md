# N-Pendulum Simulation (C# / WinForms)

A Windows Forms simulation of an **N-link pendulum** with trail rendering and pluggable numerical ODE integrators. Built to explore coupled rigid-body dynamics, linear system solving, and step-size/solver behavior in C#.

## Features

- **Coupled N-Link Dynamics:** Assembles the mass coupling matrix and force vector for an arbitrary number of pendulum links ($N$) and solves for angular accelerations ($\ddot{\theta}$) using a LU decomposition linear solver.
- **Pluggable Numerical Solvers:** Switch between **Runge-Kutta 4 (RK4)**, **Symplectic Euler**, and **Leapfrog** integrators via `IPendulumSolver` and `SolverType`.
- **Fluent Pendulum Builder & Presets:** Configure initial angles ($\theta$) and angular velocities ($\dot{\theta}$) using `NPendulumBuilder` (exact values, variations, random ranges, or various presets).

## Project Structure

- `Pendulum` - WinForms entry point (`Program.cs`), main window and render/simulation loop (`Form1.cs`), `DoubleBufferedPanel.cs`, and `NPendulumBuilder.cs`.
- `Pendulum.Math` - Pendulum state (`NPendulum.cs`), `NxNLUSolver.cs` (LU decomposition & forward/back substitution), `NumberRange<T>.cs`, `OurExtensions.cs`, and `Utils.cs`.
- `Pendulum.Math.Solvers` - `IPendulumSolver.cs`, `PendulumSolverBase.cs`, `RungeKutta4.cs`, `Leapfrog.cs`, and `SymplecticEuler.cs`.

## Prerequisites

- .NET SDK (Windows target for `System.Windows.Forms`) on Windows.

## Installation

There are no prebuilt releases yet - build from source:

```powershell
mkdir n-pendulum
cd n-pendulum
git clone git@github.com:WannaCry1LoL/N-Pendulum.git .
dotnet restore
dotnet run
```
