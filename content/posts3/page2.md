---
title: "Academia"
date: 2022-02-11T04:35:10-06:00
---

## Research

#### DSLs Importance

Powerful DSLs can be constructed for the operation of the robotic system. Hardware DSLs can also be created that monitor different subsystems such as battery depletion.  The state space of the system can be thoroughly searched and verified.  Heisenbugs that only show up in rare instances over long periods of time, can be uncovered using the P model checker. Not only can systems be modeled and tested, but the code for running the system can be auto generated from the models. The P drone example shown in the Real World Application section combines a P model with foreign functions to interface with the MavSDK library.  The model is used to generate C code, which is used to run the simulation of the drone.

## Education

In the future, we want to learn to integrate hardware DSLs to model additional aspects of the system, such as battery consumption. This, for instance, allows automated reasoning over both flight plans and battery consumption. It can also be used in case of emergencies where critical information is needed to make critical decisions.

#### Proving Correctness