# Numerical Experiments
In this repo, I will introduce some interesting examples of differential equations and illustrate different types of qualitative behaviour of numerical methods. 


# I. The Lotka-Volterra Model
![01predators-phenomena_16x9](https://user-images.githubusercontent.com/92335176/234765879-7d69a36a-b05d-49c4-a38d-9e5f4d8312f1.jpg)
[Credit.](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.nationalgeographic.com%2Fanimals%2Farticle%2Fworld-top-predators-endangered-prey&psig=AOvVaw0Hc_9ycImx1CnBlzpDIHjK&ust=1682654466999000&source=images&cd=vfe&ved=0CBMQjhxqFwoTCKjI8cCWyf4CFQAAAAAdAAAAABA5)


Predator-prey dynamics is a classic problem in ecology and mathematical biology, which involves modeling the interactions between two species, where one species (the predator) consumes the other (the prey) for sustenance. The Lotka-Volterra model is one of the earliest and simplest models for describing these interactions.

The model consists of a set of ordinary differential equations that describe the rate of change of the populations of the predator and prey species over time. Let u(t) and v(t) be the population sizes of the prey and predator species, respectively, at time t. The Lotka-Volterra model assumes that the populations grow or decline exponentially, and that the growth or decline rate of each species is influenced by the other species. Specifically, the prey population grows at a rate proportional to its size, but is reduced by predation by the predator species, while the predator population declines at a rate proportional to its size, but is enhanced by consuming the prey species. The equations for the Lotka-Volterra model are:

$$ \dot{u} = au - buv $$

$$ \dot{v} = -cv + duv $$

where a, b, c, and d are positive constants. The first equation represents the rate of change of the prey population, and the second equation represents the rate of change of the predator population.

The model has several interesting features, such as the existence of limit cycles, which represent oscillations in the population sizes of the predator and prey species over time. The model also predicts the possibility of population collapses or extinctions, if the predation rate is too high or if the carrying capacity of the environment is exceeded.

To visualize the behavior of the model, one can plot the vector field, which shows the direction and magnitude of the system's behavior at different points in the phase space, the phase portrait, which shows the trajectory of the prey-predator system over time, and the invariant curves, which correspond to a constant value of the system's invariant quantity. These plots help to understand the qualitative behavior of the system and its dependence on the model parameters.

### **Vector Field**: 
The vector field plot shows the direction and magnitude of the system's behavior at different points in the phase space. The plot uses arrows to indicate the direction of change in the prey and predator populations, and the length of the arrows represents the magnitude of the change. The plot shows that the arrows point towards the stable equilibrium point at (10, 2), indicating that the system tends towards this point. The plot also shows that the magnitude of the arrows is larger in the region of the phase space where the prey population is low and the predator population is high, indicating that the predation rate is higher in this region.
![1](https://user-images.githubusercontent.com/92335176/234765960-41af1956-8970-496c-bd3e-1242de1bf1e7.jpg)



### **Phase Portrait**: 
The phase portrait plot shows the trajectory of the prey-predator system over time in the phase space, with the prey population on the x-axis and the predator population on the y-axis. The plot shows the existence of a stable equilibrium point at (10, 2), where the prey and predator populations remain constant. The plot also shows the limit cycle, which represents the oscillations in the population sizes of the predator and prey species over time. The limit cycle encloses the stable equilibrium point, indicating that the population sizes oscillate around this point.

![2](https://user-images.githubusercontent.com/92335176/234765969-d4902687-ce0c-4803-9dfe-7d7344fc7286.jpg)



### **Invariant Curves**: 
The invariant curve plot shows the trajectories of the prey-predator system that correspond to a constant value of the system's invariant quantity. In this case, the invariant quantity is the total population size, which is the sum of the prey and predator populations. The plot shows three invariant curves, which correspond to total population sizes of 10, 20, and 30. The curves show that the trajectories of the system are confined to these curves, and that the trajectories spiral inwards towards the stable equilibrium point at (10, 2) as the total population size decreases. The curves also show that the trajectories diverge outwards from the stable equilibrium point as the total population size increases, indicating that the system becomes unstable at high population sizes.

![3](https://user-images.githubusercontent.com/92335176/234765978-d10f61ae-1918-4a50-b3f1-adb243960b23.jpg)



[Jupyter notebook](https://github.com/Phatimah/Numerical_Experiments/blob/main/Lotka-Volterra_Fig.1.1.ipynb).






## First Numerical Methods

[This notebook]() implements three numerical methods for solving an initial value problem (IVP) of the form:

$$y'(t) = f(t, y(t)),     y(t_0) = y_{0}$$

where $y(t)$ is an $n$-dimensional vector-valued function of time $t$, $f$ is a given $n$-dimensional function of $t$ and $y$, and $y_{0}$ is the initial condition at time $t_{0}$.

The three numerical methods implemented are:
- Explicit Euler method
- Implicit Euler method
- Symplectic Euler method

For each method, we solve the following IVP:

$$y'(t) = y(t),     y(0) = [1, 0]$$

which corresponds to a simple harmonic oscillator with angular frequency $1$.

### Explicit Euler method

The Explicit Euler method is a first-order one-step method that approximates the solution $y(t)$ at time $t$ by computing:

$$ y_{i+1} = y_i + h f(t_i, y_i)$$

where $h$ is the step size, $t_i$ is the current time, and $y_i$ is the approximation of $y(t_i)$. This method is explicit because $y_{i+1}$ depends only on $y_i$ and $f(t_i, y_i)$.

The following plot shows the numerical solution obtained with the Explicit Euler method for $h = 0.1$, $0.05$, and $0.025$:

<img width="248" alt="Screen Shot 2023-05-04 at 12 44 26 PM" src="https://user-images.githubusercontent.com/92335176/236170201-330b7044-2578-4209-a065-7ed8f62b03a7.png">

As the step size $h$ decreases, the numerical solution becomes more accurate and oscillates with a smaller amplitude around the exact solution $y(t) = [cos(t), sin(t)]$.

### Implicit Euler method

The Implicit Euler method is a first-order one-step method that approximates the solution $y(t)$ at time $t$ by solving the nonlinear equation:

$$y_{i+1} = y_i + h f(t_{i+1}, y_{i+1})$$

for $y_{i+1}$, where $t_{i+1}$ = $t_i$ + $h$. This method is implicit because y_{n+1} depends on $f(t_{i+1}, y_{i+1})$ which is not known in advance.

The following plot shows the numerical solution obtained with the Implicit Euler method for $h = 0.1, 0.05$, and $0.025$:

<img width="240" alt="Screen Shot 2023-05-04 at 12 44 59 PM" src="https://user-images.githubusercontent.com/92335176/236172944-8de4210c-0075-4da6-884e-d71db6658cc8.png">

As the step size $h$ decreases, the numerical solution becomes more accurate and oscillates with a smaller amplitude around the exact solution $y(t) = [cos(t), sin(t)]$.

### Symplectic Euler method

The Symplectic Euler method is a first-order one-step method that approximates the solution $y(t)$ at time $t$ by computing:

$$u_{i+1} = u_i + h f(t_i, u_i)$$

$$v_{i+1} = v_i + h v_{i+1}$$

where $u_i = y'_i$ and $v_i = y_i$, and the subscripts denote the time step. This method is symplectic because it preserves the symplectic structure of Hamiltonian systems, which are systems that satisfy certain physical and mathematical properties.

The following plot shows the numerical solution obtained with the Symplectic Euler method for $h = 0.1$, $0.05$, and $0.01$:

<img width="244" alt="Screen Shot 2023-05-04 at 12 45 07 PM" src="https://user-images.githubusercontent.com/92335176/236173019-7a1cf6b2-c325-429e-84b3-b65cb108d40f.png">

Finally, we compare the results obtained with the three numerical methods. The following plot shows the numerical solutions obtained with the Explicit Euler, Implicit Euler, and Symplectic Euler methods for h = 0.1:

<img width="1545" alt="Screen Shot 2023-05-04 at 12 59 58 PM" src="https://user-images.githubusercontent.com/92335176/236173199-67c57ab7-d8f4-439a-abcc-6321cb79ec5e.png">

From the plot, we can see that the Explicit Euler method overestimates the population sizes, while the Implicit Euler method underestimates them. On the other hand, the Symplectic Euler method provides accurate approximations that oscillate around the exact solution.

In summary, the Explicit Euler and Implicit Euler methods are not suitable for approximating the solutions of the Lotka-Volterra model, due to their instability and inaccuracy. On the other hand, the Symplectic Euler method is a stable and accurate numerical method that can be used to solve this model.



# II. The Pendulum as a Hamiltonian System

https://github.com/Phatimah/Numerical_Experiments/blob/main/fig2.ipynb

### Reference
- 



