# Reproducing and Evaluating “Next Generation Reservoir Computing” using ReservoirPy

This project reproduces and evaluates the **Next Generation Reservoir Computing (NGRC)** approach described in the paper *“Next Generation Reservoir Computing” (Gauthier et al., 2021)* using the **ReservoirPy** Python library.

The goal of the project is to explore the ability of NGRC models to **predict and reconstruct chaotic dynamical systems**, comparing their performance with traditional reservoir computing approaches.

## Overview

Reservoir Computing (RC) is a machine learning technique designed for **time-series prediction**, where past values are used to predict future system states.

Traditional reservoir computing uses a **recurrent neural network with fixed random internal connections**, where only the output layer is trained.

Next Generation Reservoir Computing (NGRC) replaces the random reservoir with a **Nonlinear Vector Autoregression (NVAR)** formulation, which improves:

- interpretability
- reproducibility
- training efficiency

Instead of using random recurrent connections, NGRC constructs **feature vectors composed of delayed system states and nonlinear polynomial combinations of them**.

## Features

- Implementation of **Next Generation Reservoir Computing (NVAR)**
- Chaotic system prediction experiments
- Evaluation using **Normalized Root Mean Square Error (NRMSE)**
- Experiments with simulated and real datasets
- Visualization of predicted vs real system trajectories

## Experiments

### 1. Lorenz Attractor Forecasting

The Lorenz attractor is a chaotic system defined by the differential equations:

dx/dt = 10(y − x)
dy/dt = x(28 − z)
dz/dt = xy − 8z/3


The experiment generates a Lorenz time series and trains an **NVAR model** to predict the evolution of the system.

The results show that NGRC is capable of accurately predicting the chaotic trajectory of the system.

### 2. Double Scroll Attractor Forecasting

The NGRC model is applied to a **double scroll chaotic system**, demonstrating its ability to model nonlinear dynamical behavior.

The predicted system trajectory closely follows the ground truth behavior.

### 3. Reconstruction of the Lorenz System

Another experiment attempts to reconstruct the **z coordinate** of the Lorenz system using only the **x and y coordinates**.

The trained model successfully predicts the missing coordinate, demonstrating the capability of reservoir computing to reconstruct hidden system variables.

### 4. Double Pendulum Experiments

The double pendulum is a well-known chaotic physical system.

Multiple experiments were performed using:

- mathematically generated datasets
- datasets generated using the `dysts` chaotic systems library
- real experimental datasets

Features used included:

- θ₁ and θ₂ (pendulum angles)
- angular velocities
- trigonometric transformations (sinθ, cosθ)

Results show that the model captures the **chaotic nature of the motion**, although predictions diverge after a certain number of time steps due to the inherent instability of chaotic systems.

### 5. Rabinovich–Fabrikant System

The Rabinovich–Fabrikant system is another nonlinear chaotic system defined by:

x' = y(z − 1 + x²) + γx
y' = x(3z + 1 − x²) + γy
z' = −2z(α + xy)


Experiments demonstrate that the NGRC model can reproduce the **chaotic attractor structure** of the system, though results are sensitive to the initial conditions.

## Installation

### Install Python

Install **Python 3.12** from the official website:

https://www.python.org/downloads/

### Install Dependencies

pip install matplotlib numpy reservoirpy ipython notebook


Alternatively create a `requirements.txt`:

matplotlib
numpy
reservoirpy
ipython
notebook

and run:

pip install -r requirements.txt


## Running the Project

Run the Jupyter notebook containing the experiments:

jupyter notebook


Then execute the notebook step-by-step to reproduce the experiments and visualizations.

## Technologies Used

- Python
- ReservoirPy
- NumPy
- Matplotlib
- Jupyter Notebook

## Results

The experiments demonstrate that **Next Generation Reservoir Computing is capable of modeling complex nonlinear dynamical systems**, including chaotic attractors.

However, for highly chaotic systems such as the double pendulum, predictions eventually diverge due to sensitivity to initial conditions.

## References

Gauthier, D. J., Bollt, E., Griffith, A., & Barbosa, W. A. (2021).  
**Next Generation Reservoir Computing.**  
Nature Communications.

Rabinovich, M. I., & Fabrikant, A. L. (1979).  
Stochastic self-modulation of waves in nonequilibrium media.

Sakemi, Y., Morino, K., Leleu, T., & Aihara, K. (2020).  
Model-size reduction for reservoir computing by concatenating internal states through time.

## Authors

- Radu Răzvan Slăvescu
- Julien Iancu
- Tudor Bartha
