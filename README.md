**Research and Development / AI – Parametric Curve Estimation**

**Problem Statement**

The goal is to determine the values of the unknown parameters **θ**, **M**, and **X** in the following parametric equations:

x = (t * cos(θ) - e^(M|t|) * sin(0.3t) * sin(θ) + X)
y = (42 + t * sin(θ) + e^(M|t|) * sin(0.3t) * cos(θ))


**Unknown Parameters:**

0° < θ < 50°
-0.05 < M < 0.05
0 < X < 100


**Parameter Range:**

6 < t < 60


**Given Data:**

A set of real curve points is provided in the dataset file `xy_data.csv`, which contains the observed ((x, y)) coordinates for values of (t) in the given range.


Objective

Estimate the unknown parameters (**θ**, **M**, **X**) such that the generated curve best fits the given data points from `xy_data.csv`.

The accuracy is evaluated using **L1 distance** (Manhattan distance) between uniformly sampled points of the **predicted** and **expected** curves.

 **Approach**

1. **Data Loading**

   * Loaded the provided `xy_data.csv` containing the real (x, y) points.
   * Normalized and cleaned the data for processing.

2. **Model Definition**

   * Defined the parametric equations for x(t) and y(t) using NumPy.
   * Parameters θ, M, and X were treated as variables to optimize.

3. **Optimization**

   * Used **`scipy.optimize.minimize`** (or curve fitting) to minimize the L1 loss between the predicted and actual curve points.
   * Implemented bounds for parameters based on the given range.
   * Multiple initialization points were tested to avoid local minima.

4. **Error Metric**

   * Computed **L1 distance** between the predicted and actual points.
   * The configuration with the **lowest L1 distance** was selected as the best solution.

5. **Visualization**

   * Plotted the fitted curve and the original data points using Matplotlib to visually verify the quality of the fit.



**Results**

The estimated parametric equations are:

x(t) = t*cos(θ*) - e^(M*|t|) * sin(0.3t) * sin(θ*) + X*
y(t) = 42 + t*sin(θ*) + e^(M*|t|) * sin(0.3t) * cos(θ*)

Where the optimized values are approximately:

θ* = [28.117]°
M* = [0.02138]
X* = [54.899]



**Tools and Libraries Used**

* **Python 3.10+**
* **NumPy** – Numerical computation
* **Pandas** – Data manipulation
* **SciPy** – Optimization and curve fitting
* **Matplotlib** – Visualization and curve plotting
* **Google Colab** – Development environment


**Evaluation Criteria**

| Criteria           | Description                                      | Max Score |
| ------------------ | ------------------------------------------------ | --------- |
| Curve Fit Accuracy | L1 distance between predicted and expected curve | 100       |
| Explanation        | Step-by-step explanation                         | 80        |
| Code Quality       | Implementation and clarity                       | 50        |




**Author**

**Name:** Meghana Mahipathi
**University:** SRM University AP
**Course:** Research and Development / Artificial Intelligence
**GitHub:** [@Mahipathi28](https://github.com/Mahipathi28)

