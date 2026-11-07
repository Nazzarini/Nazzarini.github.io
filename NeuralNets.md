# What's a Neural Network
After 2 years in my MSDS program, I have finally and briefly encountered neural networks. The term has been so prevalent in the past 5 years, that I feel like I already 'know' what a neural network is. However, some may still not have any clue, and those who do have some exposure to them may still not work intimately enough with them. So, in this post I will break down what I have learned thus far to hopefully provide something useful to anyone who might read this. I of course created a Claude artifact to help visualize and aid in my explanation:

[Claude artifact](https://claude.ai/artifact/BN1b8RqNRkuARgisBJPen1)

## Basic Explanation and Little Use Case 
I could explain the architecture of a neural network here, but I don't think that is the most basic, useful definition/explanation, so that is explained in the next section below. 

A neural network is literally just a function. While it is much more complicated than f(x)=5x, it is just a function nonetheless. Instead of x being a single number, it is usually a multidimensional input. For example, in image recognition, the input (x) could be a vector of grey scale values of the pixels in the image, which is a list of numbers. The output could be rounded up/down to a 0 or 1. The output of 0 or 1 could be interpreted as meaning True or False for whether the image is a hotdog for example. Please watch this video from Silicon Valley that is hilarious 😂.

[Silicon Valley Skit](https://youtu.be/ACmydtFDTGs?si=vKi5Eh9rZNhZ8y6Y)

One benefit of neural networks in practice that I have seen in my own domain and career as an Account Manager for SLB is the use of Ai techniques, such as NNs, to model saltwater disposal (SWD) networks via PINNs (Physics-informed neural networks). The advantage of using what boils down to what is effectively a function is that it is extremely fast to compute. In contrast, even steady-state simulators like Pipesim can take orders of magnitude longer to solve due to the fact that they are numerically solving a system of equations. The use of PINNs is advantageous in circumstances where real-time optimization accrues savings by instantaneously recommending lowest-cost routing, maximizing facility utilization, and recommending the set-point adjustments to accomplish this across the delivery network. 

## A Little More Detail
Let's explain what makes up an actual neural network (not to be confused with a SWD network). A neural network is composed of a few main components. The input layer, the hidden layers, and the output layer.

The input layer is the vector/matrix that is given to the model to classify or predict an output label/value for (depending on whether the task is classification or regression).

The hidden layers are composed of neurons. Neurons are just tiny, intermediary functions: f( w₁x₁ + w₂x₂ + … + b ). The inner part is the weighted sum of the incoming values (which is either the inputs (x's) or previous hidden layer's outputs). It is synonymous with the inner product or dot product of a weight vector and the x vector (wT.X). The function itself represented by 'f' can be many different functions. Common ones include the ReLU or Sigmoid functions. They are known as activation functions.

Sources:

Coursework in my Machine Learning class

Claude for artifact generation, grammar, and overall technical check
