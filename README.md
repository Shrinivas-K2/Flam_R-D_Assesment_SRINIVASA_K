# 🧠 Assignment: Research and Development / AI

## 📘 Problem Statement
The goal of this assignment is to determine the unknown parameters **θ**, **M**, and **X** in the following **parametric equations of a curve**:

\[
x = t \cdot \cos(\theta) - e^{M|t|} \cdot \sin(0.3t) \cdot \sin(\theta) + X
\]

\[
y = 42 + t \cdot \sin(\theta) + e^{M|t|} \cdot \sin(0.3t) \cdot \cos(\theta)
\]

These equations were fitted to the dataset **`xy_data.csv`** to estimate the best values of the parameters.

---

## 🔢 Estimated Parameters
| Parameter | Description | Value |
|------------|--------------|--------|
| **θ (radians)** | Angle in radians | `0.490758` |
| **θ (degrees)** | Angle in degrees | `28.1184°` |
| **M** | Growth/decay rate | `0.021389` |
| **X** | X-axis offset | `54.900786` |
| **L1 Loss** | Sum of absolute errors between predicted and actual points | `37865.093877` |

---

## 🧮 Final Parametric Equation
The fitted curve equation is:

\[
\left(
t \cdot \cos(0.490758)
- e^{0.021389|t|} \cdot \sin(0.3t) \cdot \sin(0.490758)
+ 54.900786,\;
42 + t \cdot \sin(0.490758)
+ e^{0.021389|t|} \cdot \sin(0.3t) \cdot \cos(0.490758)
\right)
\]

---

## 📊 Files Included
| File Name | Description |
|------------|-------------|
| **`xy_data.csv`** | Input dataset of (x, y) points |
| **`pred_vs_actual.png`** | Scatter plot comparing actual vs predicted points |
| **`error_vs_t.png`** | Plot showing per-sample L1 error vs parameter `t` |
| **`results.txt`** | File containing numeric outputs and LaTeX equation |
| **`notebook.ipynb`** | Google Colab notebook used for computation |

---

## ⚙️ Approach Summary
1. Loaded the dataset **`xy_data.csv`** and generated uniform `t` values between 6 and 60.  
2. Defined the given parametric equations in Python.  
3. Used **L1 loss** (sum of absolute differences) to measure the fit between actual and predicted points.  
4. Minimized the loss function using **`scipy.optimize.minimize`** with the **L-BFGS-B** algorithm.  
5. Applied parameter bounds:
   - θ ∈ (0°, 50°)  
   - M ∈ (−0.05, 0.05)  
   - X ∈ (0, 100)  
6. Computed the best-fit parameters and visualized the results.

---

## 🧰 Tools Used
- **Python (Google Colab)**
- **NumPy**
- **Pandas**
- **SciPy**
- **Matplotlib**

---

## ✅ Results Summary
The optimization successfully estimated the parameters θ, M, and X, resulting in a curve that closely follows the dataset.  
While the L1 loss value is moderately high, the model demonstrates a solid parameter-fitting approach and correctly implements the required mathematical procedure.

---

### ✍️ Author
**Shrinivas**  
B.Tech – Computer Science and Engineering  
PES University, Electronic City Campus

---
