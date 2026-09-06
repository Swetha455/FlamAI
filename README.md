# Parametric Curve Parameter Estimation & Optimization

## 1. Executive Summary
This project solves for the unknown parameters ($\theta, M, X$) of the parametric curve system using global numerical optimization (Differential Evolution) and mathematical reduction.

### Solution Overview:
* **$\theta$ (Angle):** $30^\circ$ ($0.5235987756 \text{ rad}$)
* **$M$ (Exponential Growth Rate):** $0.03$
* **$X$ (X-Offset):** $55$

---

## 2. Mathematical Reduction Procedure

The parametric equations given are:
$$x(t) = t \cos(\theta) - e^{M|t|} \sin(0.3t) \sin(\theta) + X$$
$$y(t) = 42 + t \sin(\theta) + e^{M|t|} \sin(0.3t) \cos(\theta)$$

### Analytical Elimination of $t$:
To eliminate $t$ as a vector of 1,500 unknown parameters, we compute the linear combination $(x - X)\cos(\theta) + (y - 42)\sin(\theta)$:

$$(x - X)\cos(\theta) + (y - 42)\sin(\theta) = \left(t \cos(\theta) - e^{M|t|}\sin(0.3t)\sin(\theta)\right)\cos(\theta) + \left(t \sin(\theta) + e^{M|t|}\sin(0.3t)\cos(\theta)\right)\sin(\theta)$$

Expanding terms:
$$= t \cos^2(\theta) - e^{M|t|}\sin(0.3t)\sin(\theta)\cos(\theta) + t \sin^2(\theta) + e^{M|t|}\sin(0.3t)\sin(\theta)\cos(\theta)$$
$$= t \left(\cos^2(\theta) + \sin^2(\theta)\right) = t$$

Thus, $t_i = (x_i - X)\cos(\theta) + (y_i - 42)\sin(\theta)$ gives an exact evaluation for $t_i$ for any candidate parameters $(\theta, M, X)$.

---

## 3. Desmos / LaTeX Format Submission

```latex
\left(t^{*}\cos(0.5235987756)-e^{0.03\left|t\right|}\cdot\sin(0.3t)\sin(0.5235987756)+55,42+t^{*}\sin(0.5235987756)+e^{0.03\left|t\right|}\cdot\sin(0.3t)\cos(0.5235987756)\right)
```
