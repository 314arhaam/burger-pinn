# burger-pinn
A Physics-Informed Neural Network for solving Burgers' equation:

Reference paper: [Physics Informed Deep Learning (Part I): Data-driven Solutions of Nonlinear Partial Differential Equations](https://arxiv.org/abs/1711.10561)
Reference paper on author's Github pages: https://maziarraissi.github.io/PINNs/

## Introduction
In this work, a neural network is trained to solve Burgers' equation, a well-known PDE, for a given set of BCs and an IC. To train this model, certain number of points on the both boundaries and on the initial timestep were sampled, as input data, called "data" points, to compute MSE loss function, in addition to another set of points on the main domain of the problem, or "collocation" points to penalize the network in case the prediction on this set is not consistent with the governing PDE.

## Results
Profile of u(t, x) (Figure 1. in reference or [author's Github page](https://maziarraissi.github.io/assets/img/Burgers_CT_inference.png))

Plotting u(t, x) in Cartesian coordinates for t in {0.25, 0.50, 0.75} (Figure 1. in reference or [author's Github page](https://maziarraissi.github.io/assets/img/Burgers_CT_inference.png))

Plotting u(t, x) in Cartesian coordinates for more t values

\newline
2 + 2 = 4 \newline
2 + 3 = 5 \newline
\frac{2}{4} = 0.5
