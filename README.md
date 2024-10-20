### Project for the course of "Selected Topics in Mathematical Modelling and Computational Sciences"
#### John H. Halton. A Retrospective and Prospective Survey of the Monte Carlo Method. SIAM Review, 12(1):1--63, January 1970. Publisher: Society for Industrial and Applied Mathematics. 

[Course Website](jhale.github.io/selected-topics-in-mmcs/)

## Goal
Modeling and simulating the trajectory of the projectile in a 2D space (x and y), considering random factors like wind force, wind angle, and air resistance coefficient. Additionally, comparing different random sampling methods and estimating uncertainties in the prediction of the projectile's trajectory.

## Assumptions
1. **2D Model**: The projectile moves within a 2D plane with the axes x (horizontal) and y (vertical - height).
2. **Effective Forces**:
    - Gravitational force (g): Acts downward (along the y-axis).
    - Air resistance force (\(\vec{F}_d\)): Proportional to the square of the projectile’s velocity and acts in the opposite direction of the movement.
    - Wind force (\(\vec{W}(t)\)): Comprises horizontal and vertical wind forces that are variable and random in both direction and intensity.
3. **Discontinuities**:
    - Air resistance coefficient (C): Follows a normal distribution with a defined mean and standard deviation.
    - Wind force (\(\vec{W}_x(t)\) and \(\vec{W}_y(t)\)): Each component follows a normal distribution with specific means and standard deviations.
4. **Initial Conditions**: The initial speed and angle of the projectile are fixed in this model.
    - Includes air resistance forces and wind forces in the form of stochastic differential equations.
