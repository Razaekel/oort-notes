# Rotating to Target

Given:
- Current Angle - $a_0$
- Current Angular Velocity - $\omega_0$
- Maximum Angular Acceleration - $\alpha_{max}$
- Target Angle - $a_T$
- Target Angular Velocity - $\omega_T$

Need:
-  Determine when to switch to maximum deceleration from maximum acceleration in order to turn in minimum time

Need to determine when to accelerate and when to decelerate to turn to the target angle $a_T$ in the least amount of time (i.e. max acceleration/deceleration). Given that there is a max acceleration amount, can determine what the maximum angular velocity can be based on angular distance from target, accelerate if angular velocity is below that maximum angular velocity for the angular distance, or decelerate otherwise.

Determine relative angle and relative angular velocity:

Relative Angle: ${\Delta}a = a_T - a_0$

Relative Angular Velocity: ${\Delta}\omega = \omega_T - \omega_0$

Need to solve for final angular position $a_T$ and final angular velocity $\omega_T$.

Basic Kinematic Formula: $x = x_0 + {v_0}t + \frac{1}{2}{a_0}t^2$

$$
\begin{align}
a_T &= a_0 + {\omega_0}t + \frac{1}{2}{\alpha_{max}}t^2\\
\omega_T &= \omega_0 + {\alpha_{max}}t
\end{align}
$$

or in relative terms:

$$
\begin{align}
0 &= {\Delta}a + {{\Delta}\omega}t + \frac{1}{2}{\alpha_{max}}t^2\\
0 &= {\Delta}\omega + {\alpha_{max}}t
\end{align}
$$

Solving equation (2) for t since $\omega_0$ and $\alpha_{max}$ are known, we get:

$$
\begin{align}
-\alpha_{max} * t &= {\Delta}\omega\\
\alpha_{max} * t &= -{\Delta}\omega\\
t &= -\frac{{\Delta}\omega}{\alpha_{max}}
\end{align}
$$

Now, could solve for $t$, but I think it'd be better to solve for the maximum $\omega_0$ that we can have at time $t$, and if angular velocity $\omega$ is less than that, we accelerate.

Start by substituting $t$:

$$
\begin{align}
0 &= {\Delta}a + {\Delta}\omega\left(-\frac{{\Delta}\omega}{\alpha_{max}}\right) + \frac{1}{2}\alpha_{max}\left(\frac{-{\Delta}\omega}{\alpha_{max}}\right)^2\\
0 &= {\Delta}a - \frac{{\Delta}\omega^2}{\alpha_{max}} + \frac{1}{2}\alpha_{max}\left(\frac{{\Delta}\omega^2}{\alpha_{max}^2}\right)\\
0 &= {\Delta}a - \frac{{\Delta}\omega^2}{\alpha_{max}} + \frac{1}{2}\left(\frac{{\Delta}\omega^2}{\alpha_{max}}\right)\\
0 &= {\Delta}a - \frac{1}{2}\left(\frac{{\Delta}\omega^2}{\alpha_{max}}\right)\\
\frac{1}{2}\left(\frac{{\Delta}\omega^2}{\alpha_{max}}\right) &= {\Delta}a\\
\frac{{\Delta}\omega^2}{\alpha_{max}} &= 2{\Delta}a\\
{\Delta}\omega^2 &= 2{\Delta}a * {\alpha_{max}}\\
{\Delta}\omega &= \sqrt{2{\Delta}a * {\alpha_{max}}}
\end{align}
$$

Expanding the relative terms:

$$
\begin{align}
{\Delta}\omega &= \sqrt{2{\Delta}a * {\alpha_{max}}}\\
\omega_T - \omega_0 &= \sqrt{2(a_T - a_0) * {\alpha_{max}}}
\end{align}
$$

So, if the current relative angular velocity is less than ${\Delta}\omega$ as calculated above based on relative angle and maximum acceleration, then accelerate, otherwise, decelerate.

# Alternative - Calculate Acceleration

$$
\begin{align}
a_T &= a_0 + {\omega_0}t + \frac{1}{2}{\alpha}t^2\\
\omega_T &= \omega_0 + {\alpha_{max}}t
\end{align}
$$

Solve for $\alpha$

$$
\begin{align}
0 &= {\Delta}a + \Delta\omega\left(-\frac{\Delta\omega}{\alpha_{max}}\right) + \frac{1}{2}\alpha\left(-\frac{\Delta\omega}{\alpha_{max}}\right)^2\\
0 &= {\Delta}a - \frac{\Delta\omega^2}{\alpha_{max}} + \frac{1}{2}\alpha\left(\frac{\Delta\omega^2}{\alpha_{max}^2}\right)\\
0 &= {\Delta}a - \frac{\Delta\omega^2}{\alpha_{max}} + \frac{1}{2}\frac{\alpha\Delta\omega^2}{\alpha_{max}^2}\\
0 &= {\Delta}a\alpha_{max}^2 - \Delta\omega^2\alpha_{max} + \frac{1}{2}\alpha\Delta\omega^2\\
-\frac{1}{2}\alpha\Delta\omega^2 &= {\Delta}a\alpha_{max}^2 - \Delta\omega^2\alpha_{max}\\
\frac{1}{2}\alpha\Delta\omega^2 &= -{\Delta}a\alpha_{max}^2 + \Delta\omega^2\alpha_{max}\\
\frac{1}{2}\alpha\Delta\omega^2 &= \Delta\omega^2\alpha_{max} - {\Delta}a{\alpha_{max}^2}\\
\frac{1}{2}\alpha &= \frac{\Delta\omega^2\alpha_{max} - {\Delta}a{\alpha_{max}^2}}{\Delta\omega^2}\\
\frac{1}{2}\alpha &= \frac{\Delta\omega^2\alpha_{max}}{\Delta\omega^2} - \frac{{\Delta}a{\alpha_{max}^2}}{\Delta\omega^2}\\
\frac{1}{2}\alpha &= \frac{\Delta\omega^2}{\Delta\omega^2}{\alpha_{max}} - \frac{{\Delta}a}{\Delta\omega^2}{\alpha_{max}^2}\\
\frac{1}{2}\alpha &= \alpha_{max} - \frac{{\Delta}a}{\Delta\omega^2}{\alpha_{max}^2}\\
\frac{1}{2}\alpha &= \alpha_{max}\left(1 - \frac{{\Delta}a}{\Delta\omega^2}\alpha_{max}\right)\\
\alpha &= 2\alpha_{max}\left(1 - \frac{{\Delta}a}{\Delta\omega^2}\alpha_{max}\right)
\end{align}
$$
