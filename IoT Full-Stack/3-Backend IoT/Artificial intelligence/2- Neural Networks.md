
Neural network contain an input layer and output layer and a hidden layers in between.

### The input layer
The input layer is where the neural network receives data represented as numbers.
Each input neuron represents a single feature, which is some characteristic of the data.

### The hidden layer
Once the features have data, each one sends its number to every neuron in the next layer (called the hidden layer), then each hidden layer neuron mathematically combines all the numbers it gets.

(The goal is to measure of whether the input data has a certain components)
Each neuron in the hidden layer does some slightly more complicated math and outputs a number, and then each neuron sends its number to every neuron in the next layer. which could be another hidden layer or the output layer.

### The output layer
The output layer is where the final hidden layer outputs are mathematically combined to answer the problem.

So, let's say we're just trying to label an image as a dog, the output should be if the image is a dog or not, this will present a single neuron, but if there is multiple output probability we have, every one will be presented by a neuron.
And depends on the highest probability on the output the network will take the decision.


## Deeper neural networks
It is the networks with more hidden layers to do deep learning.
Deep networks can combine input data in more complex ways to look for more complex components, and solve trickier problems.

But we can not make more and more deep network, because it means more hidden layers, so more math and more faster computer, more complex.


## BackPropagation
It is how the neural networks handle the mistakes to make sure all the neurons that contributed to an error get their math adjusted, and we'll unpack this a bit later.

The neural networks have 2 main parts:
- The architecture: it is the neurons and their connections.
- The weights: Are numbers that fine-tune how the neurons do their math to get an output.

So if the neural network makes a mistake this means that there is a weights are not adjusted correctly and we need to update them so they make better predictions next time.

### Optimisation
The task of finding the best weights for neural network architecture is called optimization.

we can use multiple techniques to make the optimisations on mathematical values, on of them is the LINEAR REGRESSION

### Linear Regression.

We start by drawing a random straight line on the graph, for example in the middle of it, then we calculate the distance between the line and each of the data point, add it all up and that gives us the error.

The goal of linear regression is to adjust the line to make the error as small as possible, which will called (**Line of best fit**)



### Loss Function
In case we have multiple input factor the output will have multiple output factors too, so the difference between the difference between the predicted answer and the correct answer is more than just one number.
In these cases, the error is presented by what's known as a loss function.

So to make the Neural network learn form the mistakes, the scientist and engineers come up with the backpropagation of the error algorithm.

The basic goal is to look at the loss function and then assign blame to neurons back in the previous layers of the network. Some neurons calculations may have been more to blame for the error than others, so their weights will be adjusted more, this information is fed backwards, this is where the idea of backpropagation comes from.

So the goal is fined the best combination of weights to achieve the lowest error.


### Learning Rate
it is how much the neuron weights get adjusted every time backpropagation happens.

### Fitting to the training data
Over time backpropagation will adjust the neuron weights, so that neural network's output matches the training data.

### Overfitting
This when we give a neural network some new data that does not adhere to the old correlation, which will produce a strange errors.
To prevent the overfitting is to keep the neural network simple.