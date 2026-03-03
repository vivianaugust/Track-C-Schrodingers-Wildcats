# Schrodinger's Wildcats: Harmonic Oscillator

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Hosted By: Girls in Quantum](https://img.shields.io/badge/Org-Girls%20in%20Quantum-blueviolet)](https://girlsinquantum.com)

This project was completed for the **Girls in Quantum Q-volution QHackathon 2026 Track C**

## 📖 Overview

In this project, we implement the theoretical algorithm for solving linear differential equations outlined in "A Quantum Algorithm for Solving Linear Differential Equations: Theory and Experiment" by Tao Xin et al. (2020), and apply it to the case of a quantum harmonic oscillator to find its potential and kinetic energies over the time interval [0,1].

We implemented this algorithm through Classiq, a software which allows for easy and high-level quantum circuit construction. 

---

## 💻 Running the Code

Our code is implemented using a Jupyter Notebook, allowing the user to individually run cells of the code at a time. This section will be outlining what each chunks of cells in the code accomplishes to get to our final goal of calculating the harmonic oscillator's energy. 

### 1: Library Installation {first three cells} 📚

to run our code, we will be using the Classiq environment and other Python libraries.  

### 2: Implementing the Paper in The Simplest Case 📝
This code is a full recreation of the paper, which can be used to solve for the kinetic and potential energies for a certain given time (t). Currently, the notebook is set to run the simplest case (t = 0, k = 1), but feel free to change these values!

#### a) Calculating Constants
We create a list of the coefficients C_m through the formula mentioned in the paper. This will be used to create our V and W operators that act on the second ancilla register. 

#### b) Operator Creation 
We create the V_s1 operator by implementing a function which makes a unitary matrix with the first row being the list of C_m values. We then create the V, U_x, W, and W_s1 through the use of the Z gate, H gate, and Hermitian of V_s1. We also create the U_m matrix by finding the powers of the matrix in our linear differential equation. 

Note that because the superposition of the first ancilla register will stay in |0>, we will not have to create V_s2, W_s2, or U_b matrices because the superposition of the first ancilla register will stay in |0>. This makes mathematical sense  because b = 0 in our linear equation and V is the Z gate. 

#### c) Model Generator
We apply the operators to the system in the order outlined in the paper, and are able to extract the final state of the system as well as the potential and kinetic energies of the oscillator system for the specified time! 

### 2: Algorithm Scailing & Graph Analysis 📈
Now we shift from single uses of the algorithm that focus on theoretical simularities with the paper to large-scale simulations of the quantum harmonic oscillator. We will still be using the same algorithm, just shifting our framework to focus on how different parameters affect the algorithm's performance. 

#### a) Set Up the Algorithm
Although the general algorithm is the same, we edit it to be more efficient (such as using inplace_prepare_amplitudes) and collect more data about circuit depth, width, error, and shots. 

#### b) Automated Parameter Sweeps (Data Collection)
To better understand the limitations of our quantum system, we evaluate the algorithm over three areas: time evolution, convergence analysis, and hardware efficiency. 

#### c) Graphing Our Analysis
We create four different graphs. The first one looks at how the kinetic and potential energies of our quantum harmonic oscillator evolve over time. The second looks at how the error in the energy is effected by truncation of the Taylor expansion. The last two analyse how the circuit depth and width are effected by the truncation of the Taylor Expansion

### 3: Compairson with HHL Algorithm 🧮
HHL is another famous quantum algorithm used to solve linear differential equations. We wanted to compare the tradeoffs for each algorithm by analyzing circuit width and depth. 

#### a) Set Up the LCU Algorithm
The LCU (Linear Combination of Unitaries) algorithm is the same algorithm that we have been using.

#### b) Set up the HHL Algorithm
This quantum algorithm has been around for almost 17 years and is one of the most well-known algorithms for solving linear differential equations. 

#### c) Analyze and Compare Algorithms 
We compare the circuit width and the circuit depth needed for each algorithm.

### We want to again thank **Girls in Quantum**,**Classiq**, and also any other contributors who make efforts like this hackathon and the quantum industry possible!
