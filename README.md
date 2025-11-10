Assignment: Research and Development / AI
Problem Statement

The goal of this assignment is to find the unknown parameters θ, M, and X in the following parametric equations of a curve:

𝑥
=
𝑡
⋅
cos
⁡
(
𝜃
)
−
𝑒
𝑀
∣
𝑡
∣
⋅
sin
⁡
(
0.3
𝑡
)
⋅
sin
⁡
(
𝜃
)
+
𝑋
x=t⋅cos(θ)−e
M∣t∣
⋅sin(0.3t)⋅sin(θ)+X
𝑦
=
42
+
𝑡
⋅
sin
⁡
(
𝜃
)
+
𝑒
𝑀
∣
𝑡
∣
⋅
sin
⁡
(
0.3
𝑡
)
⋅
cos
⁡
(
𝜃
)
y=42+t⋅sin(θ)+e
M∣t∣
⋅sin(0.3t)⋅cos(θ)

These parameters were estimated by fitting the model to the given dataset xy_data.csv using numerical optimization.

Estimated Parameters
Parameter	Description	Value
θ (radians)	Angle in radians	0.490758
θ (degrees)	Angle in degrees	28.1184°
M	Growth/decay rate	0.021389
X	X-axis offset	54.900786
L1 Loss	Total absolute error between predicted and actual points	37,865.093877
Final Parametric Equation

The fitted curve can be written as:

(
𝑡
⋅
cos
⁡
(
0.490758
)
−
𝑒
0.021389
∣
𝑡
∣
⋅
sin
⁡
(
0.3
𝑡
)
⋅
sin
⁡
(
0.490758
)
+
54.900786
,
  
42
+
𝑡
⋅
sin
⁡
(
0.490758
)
+
𝑒
0.021389
∣
𝑡
∣
⋅
sin
⁡
(
0.3
𝑡
)
⋅
cos
⁡
(
0.490758
)
)
(t⋅cos(0.490758)−e
0.021389∣t∣
⋅sin(0.3t)⋅sin(0.490758)+54.900786,42+t⋅sin(0.490758)+e
0.021389∣t∣
⋅sin(0.3t)⋅cos(0.490758))
📊 Files Included
File Name	Description
xy_data.csv	Input dataset of (x, y) points
pred_vs_actual.png	Scatter plot comparing actual vs predicted points
error_vs_t.png	Plot showing error vs parameter t
results.txt	File containing numeric outputs and LaTeX equation
notebook.ipynb	Google Colab notebook used for computation
⚙️ Approach Summary

Loaded the dataset xy_data.csv and generated uniform values of t in the range 6–60.

Defined the given parametric equations in Python.

Used L1 loss (sum of absolute differences) as the error metric.

Minimized the loss using scipy.optimize.minimize with the L-BFGS-B algorithm.

Applied parameter bounds:

θ ∈ (0°, 50°)

M ∈ (−0.05, 0.05)

X ∈ (0, 100)

Computed the best-fit parameters and generated visualizations to validate the fit.

 Tools Used

Python (Google Colab)

NumPy, Pandas, SciPy, Matplotlib

 Results Summary

The model successfully estimated all three unknown parameters, achieving a consistent fit between the predicted and actual curve data.
Even though the L1 loss value is moderately high, the generated curve closely follows the trend of the provided dataset, demonstrating a correct optimization setup and approach.
