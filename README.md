
# Assignment: Research and Development / AI

## Problem
Fit parameters θ, M, X for the parametric curve:

\[
x = t * \cos(\theta) - e^{M|t|} * \sin(0.3t) * \sin(\theta) + X
\]
\[
y = 42 + t * \sin(\theta) + e^{M|t|} * \sin(0.3t) * \cos(\theta)
\]

## Estimated Parameters
- θ (radians): 0.490758
- θ (degrees): 28.1184°
- M: 0.021389
- X: 54.900786
- L1 loss (sum of absolute errors): 37865.093877

## LaTeX Equation

\[
\left(
t*\cos(0.490758)
- e^{0.021389|t|} \cdot \sin(0.3t) \sin(0.490758)
+ 54.900786,
\;
42 + t*\sin(0.490758)
+ e^{0.021389|t|} \cdot \sin(0.3t) \cos(0.490758)
\right)
\]

## Files Included
- `xy_data.csv` — Input dataset
- `pred_vs_actual.png` — Visualization of actual vs predicted points
- `error_vs_t.png` — Error plot
- `results.txt` — Numeric outputs
- `notebook.ipynb` — Google Colab notebook

## Approach Summary
1. Loaded provided `xy_data.csv` and generated uniform `t` between 6 and 60.
2. Defined the given parametric equations in Python.
3. Used **L1 loss** (sum of absolute differences) to measure fit.
4. Minimized loss with **scipy.optimize.minimize** using L-BFGS-B and parameter bounds:
   - θ ∈ (0°, 50°)
   - M ∈ (−0.05, 0.05)
   - X ∈ (0, 100)
5. Computed best-fit parameters and plotted results.
