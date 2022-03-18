---
title: "Real World Application"
date: 2022-02-11T04:35:10-06:00
---

## Overview
P is a state machine based programming language for modeling and specifying complex distributed systems.  P allows programmers to model their system as a collection of communicating state machines.  P supports several backend analysis engines such as model checking and symbolic execution.  P can be systematically tested and compiled into executable code.  Combining P with MavSDK, which is a collection of libraries to interface with the MAVLink drone messaging framework, creates a powerful simulation and testing environment for drone robotics systems.  MavSDK can manage one or more vehicles via MAVLink.  MavSDK communicates with the PX4 flight stack and all testing is done against PX4.  Coupled with QGroundControl, a full simulation environment can be set up to test a distributed drone system before real-world deployment.

## Drone Example

- Created representative drone example
    - Quadrotor running open-source PX4 autopilot software
- Backend communication uses MavSDK
    - MavSDK: C++ library wrapped around MavLink to communicate with PX4


- P state machines model the flight controller:
    - Flight controller
    - MavSDK communication
    - Monitors
    - Foreign function definitions
- Synchronous functions in MavSDK
    - Example: we want to know when drone reaches takeoff altitude --> implemented by polling




- Testing: generate C# code that is used to test with Coyote (P Model Checker)
    - Liveness spec: ensure you don’t stay in a hot state of “pending request”
    - Safety spec: check that state transition sequence is correct
        - Caught issues with model
- Simulation: generate C code
    - The P-generated glue code is run in the loop