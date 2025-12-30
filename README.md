A modular Finite State Machine–based enemy AI system built in Unity to control a robot enemy with patrol and alert behaviors.

This project focuses on clean AI architecture, separating what the enemy does (states) from when it changes behavior (transitions).




https://github.com/user-attachments/assets/a1def6d6-bb1c-47a5-929e-399ffd3806e0


✨ Overview
The enemy robot operates using a custom FSM framework, where:

Each behavior is a State

States define OnEnter, OnUpdate, and OnExit

Transitions decide when to switch states using conditions

FSMs can be nested (high-level AI controlling sub-behaviors)

The result is readable, scalable, and production-friendly enemy logic.

______________________________________________________________________________________________________________________________________________________________________________

🧠 High-Level Behavior
Robot FSM (Top-Level)

Patrol FSM → Default roaming behavior

Seek & Destroy FSM → Activated when alert mode is triggered

Transitions are driven by a global alert flag (e.g. player detected)

Patrol FSM (Nested FSM)

The patrol behavior itself is an FSM composed of smaller states:

AlignToState – Rotate towards the next waypoint

MoveToState – Navigate using NavMeshAgent

AlignWithState – Match waypoint orientation

WaitState – Idle for a specified duration

Loop to next waypoint

This keeps each action focused and reusable.

______________________________________________________________________________________________________________________________________________________________________________

🧩 Core Architecture
State System

Abstract State base class

Internal state phases:

Enter

Update

Exit

Interrupted

States manage their own transitions

Transitions

Transition = Condition + Next State

Conditions are simple Func<bool>

No hard dependencies between states

FiniteStateMachine

A state that contains another state

Enables hierarchical FSMs

Clean separation between high-level intent and low-level actions

______________________________________________________________________________________________________________________________________________________________________________

🛠 Features

Custom FSM framework (no Animator-only logic)

Hierarchical state machines

NavMesh-driven movement

Animation-driven rotation & locomotion

Waypoint-based patrol with wait times

Easily extensible with new states and transitions

______________________________________________________________________________________________________________________________________________________________________________

📦 Example Use Cases

Enemy patrols

Guard AI

Robots / drones

Stealth game enemies

AI prototyping & learning FSM architecture

______________________________________________________________________________________________________________________________________________________________________________

🚀 Why FSM?

FSMs provide:

Predictable behavior

Easy debugging

Clear mental model

Scalable AI without spaghetti logic

This project prioritizes clarity over cleverness, making it suitable for real game production.
