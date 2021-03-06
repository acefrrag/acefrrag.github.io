---
    project: furuta
    type: subsect
    section: Controller Design
    title: Final Controller
---

So we can balance the pendulum if this is close enough to the upward configuration, and we can make it close to it if it is not. The last is to merge this to the controller.

Basically at every step we will compute the distance of the angle $$\alpha$$ from the ideal value ($$\alpha = 0$$). If this distance is smaller than a small value $$\epsilon$$ then we try to balance it, otherwise we apply the swing up control.

So the final form of the controller will be:

$$
Vm = \begin{cases} 
    -Kx + N\theta_{d}, & \alpha \leq \epsilon \\
    sat(\frac{R_{m}L_{r}u}{\eta_{g}K_{g}\eta_{m}k_{t}} + K_{g}k_{m} \dot \theta), & \alpha > \epsilon 
\end{cases}
$$

Where $$\theta_{d}$$ will be in the first place the $$\theta_{d}$$ measured when passing from swing up to balacing control. In this the system will not make an effort to stabilize it at that position. Then $$\theta_{d}$$ can be set to a specific value.

