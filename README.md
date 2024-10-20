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
    - Wind force $(\vec{W}(t)$): Comprises horizontal and vertical wind forces that are variable and random in both direction and intensity.
3. **Discontinuities**:
    - Air resistance coefficient (C): Follows a normal distribution with a defined mean and standard deviation.
    - Wind force (\(\vec{W}_x(t)\) and \(\vec{W}_y(t)\)): Each component follows a normal distribution with specific means and standard deviations.
4. **Initial Conditions**: The initial speed and angle of the projectile are fixed in this model.
    - Includes air resistance forces and wind forces in the form of stochastic differential equations.

## 2. Modeling Stochastic Differential Equations (SDE) in 2D with Variable Wind Force

### 2D Movement Equations:

\[
\begin{aligned}
    dX(t) &= V_x(t) \, dt \\
    dV_x(t) &= \left( -\frac{dC}{m} V_x(t) \|\vec{V}(t)\| \right) \, dt + \sigma_x dW_x(t) \\
    dY(t) &= V_y(t) \, dt \\
    dV_y(t) &= \left( -g - \frac{dC}{m} V_y(t) \|\vec{V}(t)\| \right) \, dt + \sigma_y dW_y(t)
\end{aligned}
\]

Where:
- $X(t), Y(t)$: Position of the projectile in each dimension.
- $V_x(t), V_y(t)$: Velocity of the projectile in each dimension.
- $C$: Air resistance coefficient.
- $m$: Mass of the projectile.
- $g$: Gravitational acceleration.
- $\sigma_x, \sigma_y$: Standard deviation of wind fluctuations in each dimension.
- $W_x(t), W_y(t)$: Wiener processes (stochastic processes for each dimension).

## 2. Wiener Processes:

Wiener processes \( W(t) \) for each dimension have the following properties:

- $ W(0) = 0 $
- $ W(t) $ is independent of $ W(s) $ for $ t > s $
- The distribution of $ W(s) - W(t) $ follows $ \mathcal{N}(0, t - s) $

## 3. Solving SDE: Euler-Maruyama Method

### Euler-Maruyama Method:

The Euler-Maruyama method is a simple and effective numerical technique for solving stochastic differential equations (SDE). For the equation:

$$
b(X(t), t) dW(t) + a(X(t), t) dt = dX(t)
$$

The Euler-Maruyama approximation is as follows:

$$
n b(X_n, t_n) \Delta W + a(X_n, t_n) \Delta t + n X = n+1 X 
$$

Where:
- \( \Delta W \) follows \( \mathcal{N}(0, 1) \cdot \sqrt{\Delta t} \).
