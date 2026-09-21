# Motion Planning for Self-Driving Cars in CARLA

## Overview

This project demonstrates a modular motion-planning pipeline for autonomous driving in the CARLA simulator. The system combines behavioral planning, local trajectory generation, collision checking, path selection, velocity planning, and vehicle control to navigate driving scenarios involving stop signs, static obstacles, and leading vehicles.

The project was completed as part of the University of Toronto Self-Driving Cars Specialization.

## System Workflow

```text
Driving Environment
        ↓
Behavioral Planner
        ↓
Goal State Generation
        ↓
Candidate Path Generation
(Polynomial Spirals)
        ↓
Collision Checking
        ↓
Best Path Selection
        ↓
Velocity Profile Generation
        ↓
Vehicle Controller
        ↓
CARLA Vehicle
```

## Key Components

### Behavioral Planning

Implemented behavioral planning logic to determine the appropriate driving behavior based on the current environment.

A stop-sign state machine manages transitions between normal driving, deceleration, stopping, and resuming motion.

### Local Path Generation

Generated multiple candidate local trajectories toward goal states using polynomial spiral path optimization.

These candidate paths provide alternative trajectories that can be evaluated for safety and feasibility.

### Collision Checking

Implemented circle-based collision checking to evaluate candidate paths against obstacles.

Paths that intersect detected obstacles are rejected before path selection.

### Path Selection

Evaluated collision-free candidate trajectories and selected an appropriate path based on its relationship to the desired goal trajectory.

### Velocity Planning

Generated velocity profiles for different driving situations, including:

* Normal cruising
* Deceleration and stopping
* Stop-sign behavior
* Leading-vehicle interactions

### Vehicle Control

The selected trajectory and velocity profile are passed to the vehicle-control system for trajectory tracking in CARLA.

The overall autonomous-driving stack therefore follows:

```text
Planning → Trajectory → Velocity Profile → Vehicle Control
```

## Technologies and Concepts

* Python
* CARLA Simulator
* Motion Planning
* Behavior Planning
* Path Planning
* Polynomial Spiral Trajectory Generation
* Collision Checking
* Path Selection
* Velocity Planning
* Autonomous Vehicle Control

## Demo

A CARLA simulation video demonstrates the integrated motion-planning pipeline controlling the vehicle through the driving environment.



https://github.com/user-attachments/assets/bbcf589f-84bf-4928-9e97-2531e2fe9d8d



## What I Learned

This project provided hands-on experience integrating multiple components of an autonomous-driving planning stack rather than treating planning algorithms independently.

Key areas included behavioral decision-making, trajectory generation, collision avoidance, velocity planning, and the interface between planning and vehicle control.


## Course

This project was completed as part of the University of Toronto
Self-Driving Cars Specialization on Coursera.

The repository is intended to demonstrate the project workflow,
autonomous-driving concepts, and simulation results.

This project was completed as part of the University of Toronto
Self-Driving Cars Specialization on Coursera.

The repository is intended to demonstrate the project workflow,
autonomous-driving concepts, and simulation results.
