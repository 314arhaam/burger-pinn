# burger-pinn 🍔⚛️
A Physics-Informed Neural Network for solving Burgers' equation.

Ref.: [Physics Informed Deep Learning (Part I): Data-driven Solutions of Nonlinear Partial Differential Equations](https://arxiv.org/abs/1711.10561)  
Author's Github page: https://maziarraissi.github.io/PINNs/  

Check out my other PINN project: [heat-pinn](https://github.com/314arhaam/heat-pinn)

## Introduction
This work is an implementation of the reference paper above. In this work, a neural network is trained to solve Burgers' equation, a well-known PDE, for a given set of BCs and an IC.  
To train this model, certain number of points on the both boundaries and on the initial timestep were sampled, as input data, called **data points**, to compute MSE loss function, in addition to another set of points on the main domain of the problem, or **collocation points** to penalize the network in case the prediction on this set is not consistent with the governing PDE.

### Problem details
The governing PDE is:

![Burgers' equation](https://latex.codecogs.com/svg.latex?%5Cdpi%7B120%7D%20%5Clarge%20%5C%5C%20%5Cfrac%7B%5Cpartial%7Bu%7D%7D%7B%5Cpartial%7Bt%7D%7D&plus;u%5Cfrac%7B%5Cpartial%7Bu%7D%7D%7B%5Cpartial%7Bx%7D%7D-%28%5Cfrac%7B0.01%7D%7B%5Cpi%7D%29%5Cfrac%7B%5Cpartial%5E2%7Bu%7D%7D%7B%5Cpartial%7Bx%5E2%7D%7D%3D0)

Which is solved in the following spatial and temporal domain:

![0<=t<=1 -1<=x<=+1](https://latex.codecogs.com/svg.latex?%5Cdpi%7B120%7D%20%5Clarge%20%5C%5C%200%5Cleq%7Bt%7D%5Cleq%7B1%7D%20%5C%20%2C%20%5C%20-1%5Cleq%7Bx%7D%5Cleq%7B&plus;1%7D)

Regarding the following initial and boundary conditions:

![ICBC](https://latex.codecogs.com/svg.latex?%5Cdpi%7B120%7D%20%5Clarge%20%5C%5Cu%280%2Cx%29%20%3D%20-sin%28%5Cpi%7Bx%7D%29%20%5C%5Cu%28t%2C&plus;1%29%3D0%5C%5C%20u%28t%2C-1%29%3D0)

## Results
![u(t, x)](https://latex.codecogs.com/svg.latex?%5Cinline%20u%28t%2C%20x%29) profile (Figure 1. in reference or [author's Github page](https://maziarraissi.github.io/assets/img/Burgers_CT_inference.png))  
![profile](https://github.com/314arhaam/burger-pinn/blob/main/graphics/u-profile.png)

![u(t, x)](https://latex.codecogs.com/svg.latex?%5Cinline%20u%28t%2C%20x%29) in Cartesian coordinates for ![](https://latex.codecogs.com/svg.latex?%5Cinline%20t%20%5Cin%20%5C%7B0.25%2C%200.5%2C%200.75%5C%7D) (Figure 1. in reference or [author's Github page](https://maziarraissi.github.io/assets/img/Burgers_CT_inference.png))  
![plots](https://github.com/314arhaam/burger-pinn/blob/main/graphics/u-vs-x.png)

![u(t, x)](https://latex.codecogs.com/svg.latex?%5Cinline%20u%28t%2C%20x%29) in Cartesian coordinates for more t values  
<p align=""center>
  <img src="https://github.com/314arhaam/burger-pinn/blob/main/graphics/u-constant-time.png?raw=true" alt="u-constant-time.png" width=400 height=400 />
</p>

# Note
This implementation is based on [Tensorflow 2.0](https://www.tensorflow.org/guide/effective_tf2) package and made possible by [Google Colabratory](https://colab.research.google.com) GPU.
