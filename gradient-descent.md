# Gradient Descent

This week's post addresses a question I had when learning gradient descent.  Therefore, I'm sure others have had the same question :) Machine learning is the context within which I will be talking about the gradient.

## Review & Background
Partial derivative: the rate of change of a multivariate function with respect to one variable while treating the others as constants.

Loss function: a function that measures the error (loss) of comparing a model to true measurements.  The one I believe is the most familiar loss function is the one for least squares regression, which is average of the square of the differences between the predicted values and the observed values (also known as the mean squared error - MSE) for a point xi in the training set.

Gradient Descent
Gradient Descent is best explained by separating the two terms.  The gradient is defined as the vector field that gives the direction of fastest increase.  So, by iteratively stepping in that direction we can find the minimum of the loss function.  The generalized calculation of the gradient is shown below with an example for MSE for least squares regression; the last equation is the iterative equation used for gradient descent:
![Equations](/images/post2/img1.png)

The descent part of the term doesn't really need an explanation.  The one thing I'll point out is that the gradient points in the direction of fastest increase and our objective in the context of a lot of ML problems is to minimize the loss function (aka "descend" to the minimum), so we use the negative of the gradient.  With the brief explanation of gradient descent explained, I can lay out the question that popped up for me:

Why does the gradient point in the direction of greatest ascent?  The derivative of a single variable function, f'(x), can be negative (i.e. following the x-axis decreases the value of f), so why is the multivariate version always 'positive'?

Direction of Greatest Ascent:
The way that clicked for me was visualizing it.  I've drawn up a little visualization below:
![Viz](/images/post2/img2.png)

You can see that the partial w.r.t. y = 2 (>0) in this example and the partial w.r.t. x is -1 (<0), so the partials can in fact be negative.  The reason that the gradient always points in the direction of greatest ascent is because the corresponding vector (e.g. (-1, 2)) that holds the values of the partials ends up pointing in the same direction as the positive partial components and opposite that of the negative components! 

I hope this article was as riveting to read as it was to write, haha! Even in writing this post, I found myself venturing down various rabbit holes (mainly around matrix notation, which I am still grappling with :D).

Sources:

Coursework in my Machine Learning class

ChatGPT
