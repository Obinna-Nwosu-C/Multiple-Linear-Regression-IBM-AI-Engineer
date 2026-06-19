Multiple-Linear-Regression-IBM-AI-Engineer

Multiple Linear Regression: Predicting Vehicle CO2 Emissions

[[Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[[Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.0-orange.svg)](https://scikit-learn.org/)
[[IBM AI Engineer](https://img.shields.io/badge/Course-IBM%20AI%20Engineer%20Certificate-green.svg)]
(https://www.coursera.org/professional-certificates/ibm-ai-engineer)

Project Overview
This project implements **Multiple Linear Regression** using `scikit-learn` to predict the Carbon Dioxide (CO2) emissions of various vehicles. By evaluating multiple independent variables simultaneously—specifically **Engine Size** and **Fuel Consumption (MPG)**—the model isolates the unique impact of each feature on a vehicle's environmental footprint.

This exercise demonstrates the transition from Simple to Multiple Linear Regression, highlighting how models adjust weights when dealing with correlated features.

Dataset
The analysis utilizes the (FuelConsumption.csv) dataset, sourced from the Government of Canada. It contains model-specific fuel consumption ratings and estimated CO2 emissions for new light-duty vehicles.
Target Variable: `CO2EMISSIONS` (g/km)
Selected Features: `ENGINESIZE` (Liters) and `FUELCONSUMPTION_COMB_MPG` (Miles Per Gallon)
Data Preprocessing: Features were standardized (`X_std`) to ensure fair weighting during the regression process.

Methodology
The project follows a structured machine learning pipeline:
1. Data Exploration & Standardization: Analyzed feature distributions and standardized the input variables to have a mean of 0 and a standard deviation of 1.
2. Train/Test Split: Divided the dataset into 80% training data and 20% testing data (`random_state=42`) to evaluate model generalization.
3. Simple Linear Regression (Baselines): Trained individual models for Engine Size and Fuel Consumption to establish baseline coefficients.
4. Multiple Linear Regression: Combined both features into a single model to capture their joint predictive power.
5. Visualization: Plotted the regression planes and slices to visually evaluate the goodness-of-fit against the training and testing data.

Results & Mathematical Interpretation

1. Simple Linear Regression (Individual Features)
| Feature | Coefficient (Slope) | Intercept | Interpretation |
| Engine Size | 55.18 | 256.77 | Positive correlation: Larger engines emit more CO2. |
| Fuel Consumption (MPG)| -58.51 | 256.09 | Negative correlation: Higher MPG (efficiency) reduces CO2. |

2. Multiple Linear Regression (Combined)
When both features are fed into the model simultaneously, the algorithm calculates the following parameters:
Intercept: 256.29
Coefficients: [25.27, -37.43]

Final Regression Equation: CO2 Emissions = 256.29 + (25.27 × Engine Size) - (37.43 × Fuel Consumption MPG)

Key Insight: Multicollinearity in Action
Notice that the coefficients decreased when moving from Simple to Multiple Regression (e.g., Engine Size dropped from 55.18 to 25.27). Because Engine Size and MPG are naturally correlated (larger engines typically have lower MPG), they share overlapping predictive information. The Multiple Linear Regression model intelligently adjusts the weights to prevent "double-counting", isolating the unique contribution of each variable. 

Technologies Used
Python 3.14.5
Pandas & NumPy: Data manipulation, array reshaping, and standardization.
Scikit-Learn: Model building (`LinearRegression`), train/test splitting, and evaluation.
Matplotlib: 3D plane visualization and 2D scatter plots with best-fit regression lines.

FURTHER EXPLANATION
Outcome Description: Multiple Linear Regression on CO2 Emissions

In this exercise from your IBM AI Engineer Professional Certificate, I successfully transitioned from Simple Linear Regression (using one feature) to Multiple Linear Regression (using two features) to predict vehicle CO2 emissions. 
Here is a clear breakdown of what this model achieved and the science behind the numbers:

1. The Baseline: Simple Linear Regression
First, I tested the features individually on a standardized dataset:

    Model 1 (Engine Size): Yielded a coefficient of 55.18. This confirms that as engine size increases, CO2 emissions increase.
    Model 2 (Fuel Consumption in MPG): Yielded a coefficient of -58.51. The negative sign is crucial here. It means that as fuel efficiency (MPG) goes up, CO2 emissions go down.

3. The Final Model: Multiple Linear Regression
When I combined both features into a single Multiple Linear Regression model, the algorithm produced:

    Coefficients: [25.27, -37.43]
    Intercept: 256.29

The Equation: 
CO2 Emissions = 256.29 + (25.27 × Engine Size) + (-37.43 × Fuel Consumption MPG)

Why the coefficients changed
You might notice that the coefficients dropped when combined (from 55.18 down to 25.27 for Engine Size, and from -58.51 down to -37.43 for MPG). 
This is not an error; it is a fundamental concept in machine learning. 
Engine size and MPG are highly correlated (bigger engines usually get worse gas mileage). Because they share overlapping information, the Multiple Linear Regression model "splits" the predictive weight between them to avoid double-counting. 
This demonstrates how Multiple Linear Regression isolates the unique contribution of each feature.

Course Participant/Code Executor: Obinna Nwosu C
Author: Jeff Grossman
Other Contributor(s): Abhishek Gagneja
© IBM Corporation. All rights reserved.
