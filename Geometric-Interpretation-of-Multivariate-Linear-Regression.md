# Geometric Interpretation of Multivariate Linear Regression

As I progress through my MSDS (Master's in Data Science) at UT, I wanted to start a blog distilling down different topics that I encounter in my studies into digestible posts. In doing so, I hope to provide some insights, refreshers, and even discussions for when I inevitably mess something up :)! The two promises I want to make are that I will take the time to write from my head like a luddite (quite the oxymoron) and draw any illustrations myself (in the time of Ai slop, I think it is a good promise). The timing of these posts, however, I will not make any promises. I will try to post one at least once a month but will aim for bi-weekly. For my first article, I will explain a little about linear regression (least squares regression) from a geometric viewpoint that leverages some basic linear algebra concepts. But first, a little review to make everything fall together.

## Review
1. The dot-product review: The projection of a vector onto another vector, which is proportional to the cosine between the vectors.

2. The columns of a matrix, A, can be thought of as vectors that span (create by combining in every way possible) a subspace (e.g. a plane).

3. A plane in 3-dimensions is fully described by a normal vector, n, and a point on the plane.

## Geometric Interpretation of Multivariate-LR
To me, the most intuitive and welcoming way to see linear regression is in the longhand notation I just want to mention that the coefficients in linear regression are often given beta symbols instead of w's. Like the second version below:

![intuitive notation](/images/img1.png)

While more intuitive to see spelled out, the succinct matrix notation of this is:

![matrix notation](/images/img2.png)

The notation here reads y-hat is an element of Rn. This just means that y is a vector of n items, and each item is a real number. X is similarly a matrix of m rows of n items (all real numbers). 

Now the cool part about using linear algebra to solve for the weight vector. The weight vector consists of a weight for each variable (i.e. x1, x2, etc.) and is what we want to find for our regression. The way I have seen explained most for getting these coefficients is via calculus, in which the error/loss equation is set up, a derivative is taken, and a minimum is found.

The way to do this with matrix notation does not involve calculus at all. It just relies on the fact that minimizing this error is the same as forcing the error vectors to be perpendicular to the column space of X. By enforcing this, we can find the w for the plane. To do this, remember that the error is the difference between the predicted values Xw and the y's, which is (y-Xw):

![Span X and y](/images/img3.png)

The matrix algebra is the following:

![matrix algebra](/images/img4.png)

w fully defines our regression plane. The beauty of this is that regardless of how many dimensions we have, the algebra stays the same. You can imagine how painstaking it would be to do this via calculus because you would have to take the partial derivative w.r.t. multiple variables and solve those by setting them to 0... no thank you.

I hope you found the use of linear algebra to solve what I had previously thought of as only possible with calculus as cool as I did.

## A Little Dense Aside
I do want to mention that the geometric space we are working in to do this interpretation does not need to be the same dimension as the feature space. This is actually very common for the simple fact that regression involves many samples to train the model on. The size of the training set is actually the dimension we are doing this analysis in to find w. To explain a little further, the X matrix is m rows (representing samples) and n columns (representing features x1, x2, etc.). The y (target/pred labels) is a vector of length m (one for each x). So, the column space of X spans a hyperplane in dimension-m and y is a point/vector in dimension-m. w in this context represents a combination of the column space vectors (X's columns). As y does not lay in the column space of X, we get the next best thing, the projection of y onto the hyperplane.

Sources:

Coursework in my Machine Learning class

MIT 18.06SC Linear Algebra, Fall 2011 YouTube - [16. Projection Matrices and Least Squares](https://www.youtube.com/watch?v=osh80YCg_GM&list=PLE7DDD91010BC51F8&index=18)
