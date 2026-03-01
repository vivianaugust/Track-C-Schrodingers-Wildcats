# Schrodinger's Wildcats: Harmonic Oscillator

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Hosted By: Girls in Quantum](https://img.shields.io/badge/Org-Girls%20in%20Quantum-blueviolet)](https://girlsinquantum.com)

This project was completed for the **Girls in Quantum Q-volution QHackathon 2026 Track C**

## 📖 Overview

In this project, we implement the theoretical algorithm for solving linear differential equations outlined in "A Quantum Algorithm for Solving Linear Differential Equations: Theory and Experiment" by Tao Xin et al. (2020), and apply it to the case of a quantum harmonic oscillator to find it's potential and kinetic energies over the time interval [0,1].

We implemented this algorithm through Classiq, a software which allows for easy and high-level quantum circuit construction. 

---

## 💻 Running the Code

Our code is implemented using a Jupyter Notebook, allowing the user to individually run chunks of the code at a time. This section will be outlining what each numbered chunck of the code accomplishes to get to our final goal of calculating the harmonic oscillator's energy. 

### 1: Operator Logic

Through breaking up the given second order differential equations into a system of first order equations, we obtain the linear equation form outlined in the paper (x(t) = Mx(0) + b) with M equal to the Qmod RY gate. The function "apply_m_power" outputs the respective matrix of M to some respective power N, which will be needed later in the algorithm. 

### 2: Model Generator

We create the coefficients C_m through the formula mentioned in the paper. We then prepare our two registers: one ancilla register which will encode k - the iternation value of the taylor series - and one work register which will encode x(t). Note that in the paper, they use an additional ancilla register which acts a "switch" to encode both x(0) and b into the word register. However, because b = 0 in our linear equation, it can be known that the ancilla bit will only be in the |0> state, thus being unneccessary. 

### 3: Metric Collection & Analysis

### 4: Plotting Our Graphs 


We want to again thank **Girls in Quantum**,**Classiq**, and also any other contributors who make efforst like this hackathon and the quantum industry possible!
