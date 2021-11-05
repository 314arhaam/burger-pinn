# burger-pinn
A Physics-Informed Neural Network for solving Burgers' equation.
Reference paper: [Physics Informed Deep Learning (Part I): Data-driven Solutions of Nonlinear Partial Differential Equations](https://arxiv.org/abs/1711.10561)

## Introduction
In this work, a neural network is trained to solve Burgers' equation, a well-known PDE, for a given set of BCs and an IC. To train this model, certain number of points on the both boundaries and on the initial timestep were sampled, as input data, called "data" points, to compute MSE loss function, in addition to another set of points on the main domain of the problem, or "collocation" points to penalize the network in case the prediction on this set is not consistent with the governing PDE.

## Results
Profile of ![formula](https://render.githubusercontent.com/render/math?math=u(t,x)) ()

Plotting u(t, x) in Cartesian coordinates for t in {0.25, 0.50, 0.75} ()

Plotting u(t, x) in Cartesian coordinates for more t values
