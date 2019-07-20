---
layout: post
date: 2019-06-14
title: Linear Regression
comments: true
---

### Introduction
Linear analytics is a human instinct way predict result based on limited training data. Linear Regression is the process to come out a linear model. This post will dive deeper into the mathematics conclude procedure of Linear regression.

### Simple Linear Regression
Starting from the simple linear regression. The training data is 2-dimension. x is the input data and y is the expected result. It allows us to draw a linear function in a 2-dimension coordinate system.

![linear_regression_introduction][1]

To find the best model, we're looking for a model with least square.

![least_square][2]

By expanding the least square equation, we will get a quadratic equation contians variable **k** and **b** as below. 

![quadratic_equation][3]

Now, to solve this equation, I'm going to calculate the partial derivative to **k** and **b**. Because we know that a quadratic equation must have its maximum or minimum value. In this equation, it has minimum value. By solving the partial derivative equations, we can know the corresponding value for **k** and **b** when the quadratic equation getting its minimum value.

![partial_equation][4]

Expand the equation and we get

![expand_equation][5]

Solve this equation set and we finally get

![result][6]

Now we can calculate the best model for simple linear regression.

### Multi dimension Linear Regression
For multi-dimension input, the mathematics idea is same, which is using ordinary least square method. This time, instead of having 2 equations in the set, we calculate the partial derivative for each cofficient.

![multi_dimension][7]

We will get n + 1 equations in the set and we can use the same steps to calculate the cofficient for the best model.

![multi_dimension_graph][9]

![multi_dimension_reuslt][8]


[1]: assets/Linear_Regression/Linear_Regression_introduction.png
[2]: assets/Linear_Regression/least_square.png
[3]: assets/Linear_Regression/quadratic_equation.png
[4]: assets/Linear_Regression/partial_equation.png
[5]: assets/Linear_Regression/expand_equation.png
[6]: assets/Linear_Regression/result.png
[7]: assets/Linear_Regression/multi_dimension.png
[8]: assets/Linear_Regression/multi_dimension_graph.png
[9]: assets/Linear_Regression/multi_dimension_result.png
