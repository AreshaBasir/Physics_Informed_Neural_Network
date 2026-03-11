# Physics_Informed_Neural_Network
Physics-Informed Neural Networks (PINNs) for modeling movement cost fields in robot navigation and active visual perception. The project explores balancing movement cost and information gain using physics-aware learning.

## Research Motivation

Autonomous robots must balance two competing objectives:

1. Minimizing movement cost (energy, time, distance)
2. Maximizing information gain from the environment

Traditional navigation approaches rely on discrete path planning algorithms such as A* or Fast Marching.

This project explores a **physics-informed approach** where a neural network learns a **continuous cost field** that guides robot navigation.

---

## Key Idea

A **Physics-Informed Neural Network (PINN)** is used to learn the movement cost field by enforcing a physical constraint derived from the **Eikonal equation**.

The learned field provides a continuous representation of movement cost across the environment.

Robots can navigate by following the **gradient of the learned field**.

---

## System Overview

Pipeline:

Environment → PINN Cost Field → Gradient Computation → Navigation Policy

Steps:

1. Initialize MiniGrid environment
2. Train PINN to learn movement cost field
3. Compute gradients of the learned field
4. Navigate using gradient descent toward the goal

---

## Repository Structure

pinn-navigation/
│
├── minigrid_setup.py # MiniGrid environment initialization
├── pinn_model.py # PINN architecture
├── train_pinn.py # Training script
├── navigation.py # Gradient-based navigation
├── visualization.py # Cost field and trajectory plots
├── experiments/ # Experimental scripts
└── README.md



---

## Installation

Install dependencies:
pip install gymnasium
pip install gym-minigrid
pip install deepxde
pip install torch
pip install matplotlib


---

## Running the Project

Run the training script:
python train_pinn.py


Run the navigation simulation:
python navigation.py


---

## Example Output

The model learns a **continuous movement cost field** and the robot follows the **steepest descent direction** toward the goal.

Example visualization includes:

- Movement cost heatmap
- Gradient field
- Robot trajectory

---

## Future Work

Possible extensions include:

- Integrating reinforcement learning for active navigation
- Modeling information gain for perception-driven exploration
- Scaling the method using XPINNs
- Comparing with classical algorithms such as Fast Marching

---

## Citation

If you use this repository in research, please cite:
Aresha Basir Spriha
Physics-Informed Navigation using PINNs
Undergraduate Thesis


---

## License

MIT License
