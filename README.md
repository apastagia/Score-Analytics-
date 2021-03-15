Ridge and Lasso regression:
    Ridge and Lasso regression are powerful techniques generally used for creating parsimonious models in presence of a ‘large’ number of features. Here ‘large’ can typically mean either of two things:

1. Large enough to enhance the tendency of a model to overfit (as low as 10 variables might cause overfitting)

2. Large enough to cause computational challenges. With modern systems, this situation might arise in case of millions or billions of features

Ridge and Lasso regression penalizing the magnitude of coefficients of features along with minimizing the error between predicted and actual observations. These are called ‘regularization’ techniques. The key difference is in how they assign penalty to the coefficients:

    Ridge Regression:
        -> Performs L2 regularization, i.e. adds penalty equivalent to square of the magnitude of coefficients
        
        -> Minimization objective = LS Obj + α * (sum of square of coefficients)
        
    Lasso Regression:
        -> Performs L1 regularization, i.e. adds penalty equivalent to absolute value of the magnitude of coefficients
        
        -> Minimization objective = LS Obj + α * (sum of absolute value of coefficients)
        
NOTE: Here ‘LS Obj’ refers to ‘least squares objective’, i.e. the linear regression objective without regularization.

Ridge Regression
    As mentioned before, ridge regression performs ‘L2 regularization‘, i.e. it adds a factor of sum of squares of coefficients in the optimization objective. Thus, ridge regression optimizes the following:

Objective = RSS + α * (sum of square of coefficients)

Here, α (alpha) is the parameter which balances the amount of emphasis given to minimizing RSS vs minimizing sum of square of coefficients. α can take various values:

    1. α = 0:
        * The objective becomes same as simple linear regression.
        * We’ll get the same coefficients as simple linear regression.

    2. α = ∞:
        * The coefficients will be zero. Why? Because of infinite weightage on square of coefficients, anything less than zero will make the objective infinite.

    3. 0 < α < ∞:
        * The magnitude of α will decide the weightage given to different parts of objective.
        * The coefficients will be somewhere between 0 and ones for simple linear regression.
        
How α(alpha) would impact the magnitude of coefficients. One thing is for sure that any non-zero value would give values less than that of simple linear regression.

Lasso Regression:
    LASSO stands for Least Absolute Shrinkage and Selection Operator. I know it doesn’t give much of an idea but there are 2 key words here – ‘absolute‘ and ‘selection‘.

Lasso regression performs L1 regularization, i.e. it adds a factor of sum of absolute value of coefficients in the optimization objective. Thus, lasso regression optimizes the following:

Objective = RSS + α * (sum of absolute value of coefficients)

Here, α (alpha) works similar to that of ridge and provides a trade-off between balancing RSS and magnitude of coefficients. Like that of ridge, α can take various values. Lets iterate it here briefly:

    1. α = 0: Same coefficients as simple linear regression
    2. α = ∞: All coefficients zero (same logic as before)
    3. 0 < α < ∞: coefficients between 0 and that of simple linear regression