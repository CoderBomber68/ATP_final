# The Impact of Cyclist Hand-Signaling Behaviour on Road Safety: An Agent-Based Model

This repository contains a NetLogo agent-based model simulating traffic at a four-way, unsignalized intersection. The purpose of this project is to investigate whether hand-signaling by cyclists can reduce the number of traffic accidents.

## 1. Introduction

In the Netherlands, a global cycling leader, intersections are critical hotspots for cyclist safety, with over half of cyclist fatalities occurring at these locations. While many infrastructural and behavioral factors contribute to cyclist safety, the role of hand-signaling as a behavioral intervention is an under-explored area of research.

This project introduces a novel agent-based model to fill this research gap. It simulates a traffic intersection with cars and bikes to explore how a cyclist's decision to use hand signals when turning affects the overall accident rate. The central research question is: **Does hand-signaling cyclist behaviour decrease the number of accidents?**

## 2. How The Model Works

The simulation takes place in a continuous, two-dimensional environment representing an unsignalized, unprioritized four-leg intersection.

### Agents
There are two types of agents in the model:
*   **Cars:** Represented by a blue car shape. They slow down for agents ahead and react to signaling cyclists by braking more cautiously (turning orange).
*   **Bicycles:** Represented by a red bicycle shape. A key attribute for bikes is `signaling?`, which determines if they use hand signals. This is visually indicated with custom shapes showing an arrow for the direction of the turn.

### Agent Behavior
*   **Spawning:** Cars and bikes are spawned at the edges of the simulation world and are randomly assigned a maneuver (turn left, turn right, or go straight).
*   **Intersection Rules:** The intersection is unsignalized. Agents follow right-of-way rules, yielding to agents approaching from their right and to oncoming traffic when turning left.
*   **Accidents:** An accident occurs when any two agents come within a minimum collision distance. Car-to-car collisions are excluded from the accident count to better isolate the effects of cyclist behavior. Upon crashing, agents turn yellow and are removed from the simulation after 20 ticks to prevent traffic blockage.

## 3. How to Use the Interface

The model was implemented in **NetLogo 6.4.0**. The user interface is designed for simple experimentation and observation.

*   **Buttons**:
    *   `setup`: Initializes the simulation environment.
    *   `go`: Runs the simulation continuously.
    *   `go once`: Advances the simulation by a single time step.

*   **Sliders**:
    *   `freq-to-north`, `freq-to-east`, etc.: Control the traffic density from each of the four directions.
    *   `car-speed-limit`: Sets the maximum speed for car agents.
    *   `bike-speed-limit`: Sets the maximum speed for bike agents.
    *   `percent-bikes-signaling`: The main experimental variable. This slider sets the percentage of new cyclists that will use hand signals.

*   **Output**:
    *   **Number of accidents**: A monitor displaying the total number of accidents.
    *   **Number of accidents in time**: A plot that visualizes the accumulation of accidents over the simulation's duration.

## 4. Findings

The research concluded that **cyclist hand-signaling positively impacts road safety**. The experiment showed an approximately negative linear relationship between the percentage of signaling cyclists and the number of accidents. For every 10% increase in cyclists using hand signals, the number of accidents in the simulation was reduced by approximately 1.7.

This suggests that hand-signaling improves the ability of other road users to anticipate a cyclist's maneuvers, leading to fewer collisions.

## 5. Limitations and Future Research

### Limitations
*   The model uses a simplified, linear model for acceleration and braking. Real-world vehicle dynamics are non-linear.
*   The simulation assumes an intersection with no traffic lights or signs, which limits generalizability to more complex, controlled intersections.

### Future Research
*   **Enhance Realism**: The model could be extended by adding traffic lights, priority signs, or pedestrians.
*   **Improve Vision Mechanism**: The current agent detection is a fixed cone. This could be evolved into a dynamic line-of-sight model to simulate situations where larger vehicles might obscure an agent's view of smaller ones.

## 6. References
 The information in this README is based on the project report: "The Impact of Cyclist Hand-Signalling Behaviour on Road Safety: An Agent-Based Model" by Group 5 (s5133122, s4729080, s5190584).
