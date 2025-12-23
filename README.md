# Smarter-Last-Mile-Logistics-An-Autonomous-Transport-Robot-with-Enhanced-IoT-Features-
## Abstract 

Last-mile delivery in urban environments is challenged by traffic congestion, dynamic obstacles, and unpredictable conditions. Many autonomous delivery robots rely on static routes or local-only navigation, limiting their adaptability. This project proposes an IoT-enabled autonomous delivery robot that combines cloud-based real-time route optimization with on-board obstacle avoidance through a hybrid navigation framework. By leveraging live IoT data and multi-sensor perception, the system dynamically adapts to changing environments, improving delivery time, energy efficiency, and safety. Simulation and real-world evaluations demonstrate the effectiveness of the proposed approach for scalable last-mile logistics.

## Problem Definition 

Urban last-mile delivery is affected by congestion, dynamic obstacles, and limited adaptability of existing autonomous delivery robots. Most current systems rely on static routing or local obstacle avoidance, making them inefficient and unsafe under changing conditions. The problem is to design an autonomous delivery system that can dynamically re-plan routes using real-time IoT data while ensuring safe, collision-free navigation through local sensing, with minimal impact on energy consumption and computational resources.

## IoT-Enabled Autonomous Delivery Robot with Hybrid Route Planning

This repository presents an IoT-enabled autonomous delivery robot (ADR) designed for efficient, safe, and energy-aware last-mile logistics. The system combines cloud-based global route optimization with on-board local obstacle avoidance, enabling real-time adaptation to traffic congestion, environmental risks, and dynamic obstacles.

## 🚀 Key Idea

Conventional delivery robots rely on static routes or local obstacle avoidance only, which leads to delays, energy waste, and safety risks.
This work introduces a Hybrid IoT Navigation Framework that:

1)Uses IoT cloud data (traffic, congestion, risk) for global re-routing

2)Uses multi-sensor fusion (LiDAR, camera, ultrasonic) for local collision avoidance

3)Dynamically balances time, energy, and safety

## 🧠 System Architecture

The system follows a three-layer design:

1)Perception Layer

LiDAR, camera, ultrasonic sensors

Occupancy grid & sensor fusion

2)Decision Layer

Global route planning using IoT-updated weighted graphs

Local obstacle avoidance using Dynamic Window Approach (DWA)

Hybrid re-planning logic

3)Execution Layer

Motor control with safety constraints

Continuous feedback to IoT cloud

## 📐 Hybrid Path Planning Method

1)Global Planner (IoT-assisted)

Minimizes a weighted cost:

Distance

Traffic congestion

Environmental risk

2)Local Planner (On-board)

Ensures collision-free motion

Reacts instantly to nearby dynamic obstacles

3)Hybrid Logic

Re-routes globally only when major deviations occur

Otherwise follows optimal path with local corrections

## Algorithm Hybrid_Path_Planning_ADR

```
Input:   Source node s, Destination node d, Initial path P0, Robot state X(t), IoT traffic/environmental data, Sensor inputs

Output:  Optimized collision-free path P*


Begin
│
├─ Initialize robot state X(t)
├─ Load initial route P0 from s → d
├─ Set system parameters: velocity limits, safety radius, thresholds
│
├─ While (destination d not reached) do
│   │
│   ├─ Perception Layer
│   │   ├─ Collect sensor data: LiDAR, camera, ultrasonic
│   │   ├─ Construct occupancy grid O(x,y,t)
│   │   └─ Fuse multi-sensor data for local environment map
│   │
│   ├─ IoT Data Acquisition
│   │   ├─ Receive real-time traffic, weather, and road updates
│   │   └─ Update graph edge weights W_e(t) using IoT data
│   │
│   ├─ Global Route Optimization
│   │   ├─ Compute updated global path Pg using shortest-path algorithm
│   │   └─ Minimize cost: W_e(t) = α·d_e + β·τ_e(t) + γ·ρ_e(t)
│   │
│   ├─ Local Obstacle Avoidance
│   │   ├─ Generate candidate velocities (v, ω) from Dynamic Window
│   │   ├─ For each candidate (v, ω) in admissible set:
│   │   │     └─ Evaluate cost J(v, ω) = λ1·d_goal + λ2·d_obs + λ3·v
│   │   └─ Select optimal control (v*, ω*)
│   │
│   ├─ Hybrid Re-Planning
│   │   ├─ If (unexpected blockage OR major deviation detected) then
│   │   │     └─ Trigger global re-routing using IoT data
│   │   └─ Else
│   │         └─ Follow Pg with local avoidance adjustments
│   │
│   ├─ Execution
│   │   ├─ Send (v*, ω*) to motion controller
│   │   └─ Ensure safety: maintain distance ≥ r_s from obstacles
│   │
│   └─ Performance Monitoring
│       ├─ Record travel time, energy usage, and safety margin
│       └─ Upload performance log to IoT cloud
│
└─ End While

Output final optimized path P* and performance metrics

End
```

## Flow Chart Diagram for Proposed IoT-Enabled Hybrid Path Planning Model
Figure 2, The flow of the Autonomous Delivery Robot (ADR) has been presented in the flowchart. The entire process begins with the initializing of the parameters of the robot, and perception based on Multi-Sensor fusion and Internet of Things (IoT) data. The world route planning involves the real-time update of the traffic and the environment, and the local obstacle avoidance planning makes sure that there is no collision. A hybrid re-planning module creates a balance between the globalizing rerouting means, and the localizing means of changes in case of unexpected events. The execution layer operates by converting decisions into motor commands based on the existing safety and so that on the one hand performance monitoring is involved in order to maintain a record to be constantly improved. 

<img width="449" height="665" alt="image" src="https://github.com/user-attachments/assets/822e8d08-9798-4ece-a055-a20525ac0ba7" />


## 🧪 Experimental Evaluation

Validated using:

Urban grid-based simulator

Real-world campus road testbed

Compared Strategies

1)Static routing

2)Local-only obstacle avoidance

3)Proposed Hybrid IoT approach

## Key Results

⏱ 37% faster delivery time

🔋 18% lower energy consumption (Wh/km)

🛡 97.5% collision-free runs

📉 86% reduction in collision probability

📏 18% improvement in path efficiency

Hybrid IoT consistently outperformed both baselines, especially under high congestion.

## 📊 Key Contributions

Hybrid IoT-cloud + on-board navigation framework

Congestion- and risk-aware real-time re-routing

Strong safety improvements via global foresight + local responsiveness

Extensive simulation + real-world validation

Practical insights for smart cities and autonomous logistics

## ⚠️ Limitations

Higher computational demand than static routing

Dependency on reliable IoT connectivity

Requires cybersecurity-aware deployment

## 🔮 Future Work

Edge-first lightweight planners

Federated & continual learning across robot fleets

Human-aware navigation in dense pedestrian zones

City-scale deployment and benchmarking
