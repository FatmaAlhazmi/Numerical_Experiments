# Numerical Experiments
In this repo, I will introduce some interesting examples of differential equations and illustrate different types of qualitative behaviour of numerical methods. 


## I. The Lotka-Volterra Model
![01predators-phenomena_16x9](https://user-images.githubusercontent.com/92335176/234765879-7d69a36a-b05d-49c4-a38d-9e5f4d8312f1.jpg)


Predator-prey dynamics is a classic problem in ecology and mathematical biology, which involves modeling the interactions between two species, where one species (the predator) consumes the other (the prey) for sustenance. The Lotka-Volterra model is one of the earliest and simplest models for describing these interactions.

The model consists of a set of ordinary differential equations that describe the rate of change of the populations of the predator and prey species over time. Let u(t) and v(t) be the population sizes of the prey and predator species, respectively, at time t. The Lotka-Volterra model assumes that the populations grow or decline exponentially, and that the growth or decline rate of each species is influenced by the other species. Specifically, the prey population grows at a rate proportional to its size, but is reduced by predation by the predator species, while the predator population declines at a rate proportional to its size, but is enhanced by consuming the prey species. The equations for the Lotka-Volterra model are:

$$ \dot{u} = au - buv \newline
\dot{v} = -cv + dbuv $$

where a, b, c, and d are positive constants. The first equation represents the rate of change of the prey population, and the second equation represents the rate of change of the predator population.

The model has several interesting features, such as the existence of limit cycles, which represent oscillations in the population sizes of the predator and prey species over time. The model also predicts the possibility of population collapses or extinctions, if the predation rate is too high or if the carrying capacity of the environment is exceeded.

To visualize the behavior of the model, one can plot the vector field, which shows the direction and magnitude of the system's behavior at different points in the phase space, the phase portrait, which shows the trajectory of the prey-predator system over time, and the invariant curves, which correspond to a constant value of the system's invariant quantity. These plots help to understand the qualitative behavior of the system and its dependence on the model parameters.

#### **Vector Field**: 
The vector field plot shows the direction and magnitude of the system's behavior at different points in the phase space. The plot uses arrows to indicate the direction of change in the prey and predator populations, and the length of the arrows represents the magnitude of the change. The plot shows that the arrows point towards the stable equilibrium point at (10, 2), indicating that the system tends towards this point. The plot also shows that the magnitude of the arrows is larger in the region of the phase space where the prey population is low and the predator population is high, indicating that the predation rate is higher in this region.
![1](https://user-images.githubusercontent.com/92335176/234765960-41af1956-8970-496c-bd3e-1242de1bf1e7.jpg)



#### **Phase Portrait**: 
The phase portrait plot shows the trajectory of the prey-predator system over time in the phase space, with the prey population on the x-axis and the predator population on the y-axis. The plot shows the existence of a stable equilibrium point at (10, 2), where the prey and predator populations remain constant. The plot also shows the limit cycle, which represents the oscillations in the population sizes of the predator and prey species over time. The limit cycle encloses the stable equilibrium point, indicating that the population sizes oscillate around this point.
![2](https://user-images.githubusercontent.com/92335176/234765969-d4902687-ce0c-4803-9dfe-7d7344fc7286.jpg)



#### **Invariant Curves**: 
The invariant curve plot shows the trajectories of the prey-predator system that correspond to a constant value of the system's invariant quantity. In this case, the invariant quantity is the total population size, which is the sum of the prey and predator populations. The plot shows three invariant curves, which correspond to total population sizes of 10, 20, and 30. The curves show that the trajectories of the system are confined to these curves, and that the trajectories spiral inwards towards the stable equilibrium point at (10, 2) as the total population size decreases. The curves also show that the trajectories diverge outwards from the stable equilibrium point as the total population size increases, indicating that the system becomes unstable at high population sizes.
![3](https://user-images.githubusercontent.com/92335176/234765978-d10f61ae-1918-4a50-b3f1-adb243960b23.jpg)



[Here]() you can find the full implementation.






### First Numerical Methods
**Explicit Euler Method**
**Implicit Euler Method**
**Implicit Midpoint Rule**
### References
1- 
2- https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.nationalgeographic.com%2Fanimals%2Farticle%2Fworld-top-predators-endangered-prey&psig=AOvVaw0Hc_9ycImx1CnBlzpDIHjK&ust=1682654466999000&source=images&cd=vfe&ved=0CBMQjhxqFwoTCKjI8cCWyf4CFQAAAAAdAAAAABA5



