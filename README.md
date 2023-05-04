Download Link: https://assignmentchef.com/product/solved-cs433-exercise-4-cross-validation-and-bias-variance-decomposition
<br>
Cross-Validation and Bias-Variance decomposition

Goals.       The goal of this exercise is to

<ul>

 <li>Implement 4-fold cross-validation.</li>

 <li>Understand bias-variance decomposition.</li>

</ul>

Setup, data and sample code.               Obtain the folder labs/ex04 of the course github repository

<a href="https://github.com/epfml/ML_course/tree/master/labs/ex04">github.com/epfml/ML</a> <a href="https://github.com/epfml/ML_course/tree/master/labs/ex04">course</a>

This exercise is partly based on the materials from last week (labs/ex03). If you don’t have it already, please finish the ex03 first. You might directly reuse/copy some of the functions you implemented yourself during previous exercises, e.g., ridge regression(), least squares() and split data().

<h1>1           Cross-Validation</h1>

The simple 50%-50% split of test and training data from last week’s exercise corresponds to the first phase of 2-fold cross-validation. It may not give an unbiased test error. A better way to do this is to use full <em>K</em>-fold cross-validation.

Exercise 1:

Implementing 4-fold cross-validation.

<ul>

 <li>Please COPY your code from last week, and fill in the corresponding templates, i.e., ridge regression() to ridge regression.py, build poly() to build polynomial.py, and least squares() to least squares.py.</li>

</ul>

In this exercise, please fill in the notebook function cross validation demo(), and perform 4-fold crossvalidation for polynomial degree 7. Plot the train and test RMSE as a function of <em>λ</em>. The resulting figure should look like Figure 1.

Note that we can use “numpy.random.seed(seed)” to generate two independent training and test data splits.

<ul>

 <li>How will you use 4-fold cross-validation to select the best model among various degrees, say from 2 to 10? Write code to do it.</li>

 <li>BONUS: Using cross-validation, one can also compute the variance of the RMSE, over the folds. This tells us how confident we could be of our <em>model selection</em>. You can use box-plots to do this.</li>

</ul>

<h1>2           Visualizing Bias-Variance Decomposition</h1>

In the lecture, we learned about the expected test and train error. In the following exercise, we will reproduce the figure illustrating “error vs. model complexity” of the “bias-variance” lecture notes). Read the lecture notes to understand which quantities are essential for this figure.

Exercise 2:

Visualizing the bias-variance trade-off.

Figure 1: Effect of <em>λ </em>on training and test errors, calculated using 4-fold cross-validation

<ul>

 <li>Complete the notebook function bias variance demo() and experiment with different seeds, number of training and testing examples with least square, to get a plot that looks similar to Figure 2, i.e. on average the train error should go down and test error should go up for higher degrees. NOTE that you should COPY the function split data() implemented in ex03 to the template file split data.py.</li>

 <li>Look at the variance of test errors. Does it increase with the degree of polynomial?</li>

 <li>What would you expect to happen if you replace least-squares with Ridge regression? Go through the lecture notes to understand that.</li>

 <li>BONUS: Another good visualization is to use the box-plot to get an appropriate visualization. You can clearly see the distribution of test error.</li>

 <li>BONUS: Produce the same plot with Ridge regression. You will have to automatically find the best <em>λ </em>for each degree. You do this using <em>K</em>-fold cross-validation (CV) only on the training set. So you need to insert the CV code inside. You also have to make sure that you chose an appropriate range of <em>λ</em>, so that you achieve the minimum test error.</li>

</ul>

2

Figure 2: Bias-Variance Decomposition