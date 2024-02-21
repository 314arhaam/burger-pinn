# 🍔 $\textbf{Burger-PINN}$ ⚛️
A Physics-Informed Neural Network to solving **Burgers' equation**.

Reference: [Physics Informed Deep Learning (Part I): Data-driven Solutions of Nonlinear Partial Differential Equations](https://arxiv.org/abs/1711.10561)  
Author's Github page: https://maziarraissi.github.io/PINNs/  

Check out my other PINN project: [heat-pinn](https://github.com/314arhaam/heat-pinn)

## Introduction
This work is an implementation of the reference paper above. In this work, a neural network is trained to solve Burgers' equation, a well-known PDE, for a given set of BCs and an IC.  

To train this model, certain number of points on the both boundaries and on the initial timestep were sampled, as input data, called **data points**, to compute MSE loss function, in addition to another set of points on the main domain of the problem, or **collocation points** to penalize the network in case the prediction on this set is not consistent with the governing PDE.

### Problem details
The governing PDE is:

### $\partial_{t}{u}+u\partial_{x}{u}-(\frac{0.01}{\pi})\partial_{xx}{u} = 0$

Which is solved in the following spatial and temporal domain:

### $D = \\{ (t, x)\ |\ 0\le t \le +1 \land -1\le x \le +1 \\}$

Regarding the following initial and boundary conditions:

$$
\begin{equation}
  \begin{cases}
    u(0, x) = -\sin({\pi x})\\
    u(t, +1) = 0.0 \\
    u(t, -1) = 0.0 \\  
  \end{cases}
\end{equation}
$$


## Results
$u(t, x)$ profile (Figure 1. in reference or [author's Github page](https://maziarraissi.github.io/assets/img/Burgers_CT_inference.png))  
![profile](https://github.com/314arhaam/burger-pinn/blob/main/graphics/u-profile.png)

$u(t, x)$ in Cartesian coordinates for $t \in \\{0.25,0.5,0.75\\}$ (Figure 1. in reference or [author's Github page](https://maziarraissi.github.io/assets/img/Burgers_CT_inference.png))  
![plots](https://github.com/314arhaam/burger-pinn/blob/main/graphics/u-vs-x.png)

$u(t, x)$ in Cartesian coordinates for more t values  
<p align=""center>
  <img src="https://github.com/314arhaam/burger-pinn/blob/main/graphics/u-constant-time.png?raw=true" alt="u-constant-time.png" width=400 height=400 />
</p>

# Note
This implementation is based on [Tensorflow 2.0](https://www.tensorflow.org/guide/effective_tf2) package and made possible by [Google Colabratory](https://colab.research.google.com) GPU.
