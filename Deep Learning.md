# **Deep Learning**



###### **Why**:

* Growth Data
* Hardware advancements - GPU, TPU (TensorFlow Process Unit) - started by Google
* Python and Opensource Ecosystem
* Cloud and AI Boom



###### **Frame works:**

* Tensor Flow (Keras included) - By Google
* PyTorch - By Facebook



Logistic Regression:

Activation Function / Sigmoid Function: Converts the linear equation to a S-curved shaped graph or model ranging from 0 to 1.



Tutorial upto: 8



###### **Activation Functions:**

1. Sigmoid - Range : Between 0 to 1
2. Step function - Range: Either 0 or 1
3. Tanh function - Range: Between -1 to 1
4. ReLU: for value < 0 gives 0 and for value > 0 gives the same values (for e.g. for 2 it will be 2)
5. Leaky ReLU: Tries to keep the negative values as close to zero as possible.



**General guideline**: Use **sigmoid** in output layer. All other places try to use **tanh**.



Issues with sigmoid and tanh:

Gradient i.e. derivative = delta y / delta x, how much output changes for a given change in input. Derivative is useful to back propagate the errors. But for sigmoid and tanh at end point curves where curve becomes horizontal y value doesn't change which is approximately 0. Hence derivative is also 0. This causes the error backpropagation issues. This is called VANISHING GRADIENTS.



**ReLU**: Solves the Vanishing Gradients issue. For **hidden layers** if you are not sure which activation function to use, just use **ReLU** as your default choice.





###### **Slope Vs Derivative:**

Slope:

1. Used for straight lines
2. Used for linear equations
3. Slope is constant at all points on the line/graph



Derivative:

1. Used for non-linear equations (for curves)
2. Derivative is a function i.e. across the curve the slope varies for different values of input x.



E.g. Derivative of x\*\*2 is 2x: This means that if x=5, slope=10; x=2, slope=4.



* Tangent to the curve is nothing but derivative at that point.





**Partial Derivative**: Derivative wrt a given variable treating all other variables as constants.



Neural Network: is all about adjusting weights to get the optimal result.



Derivatives and Partial Derivatives helps in achieving the same.



e.g. Partial derivative of error (y-y`) wrt age indicates whether a person will buy insurance if the age changes.





TensorFlow Loss Function Values:

* sparse\_categorical\_crossentropy
* binary\_crossentropy or log loss
* mean\_absolute\_error
* mean\_squared\_error



For logistics: log loss i.e. binary\_crossentropy is preferred as loss functions.



loss: individual error

cost/loss function: cumulative error (e.g. MAE, MSE, log loss)



###### **Gradient Descent**

Gradient Descent: Technique to find optimal weights and bias for which the loss is minimum.

Randomly assigns values of weights and bias, does optimization using loss function and updates weights and bias until optimal weights and bias obtained for which the loss is minimum.



Formula:

* weight = weight - learning\_rate \* derivative(of error wrt weight)	# derivative(or Gradient) = (1/n) \* np.dot(transpose(feature), (y\_true - y\_pred)).
* bias = bias - learning\_rate \* derivative(of error wrt bias)		# derivative(or Gradient) = np.mean(y\_true - y\_pred) i.e. mean of loss.



Types of Gradient Descent:

* Batch: Going through all the samples of dataset before adjusting the weights.
* SGD: One sample picked randomly and then weights adjusted.
* Mini-batch: Complete dataset is divided into random batches.



Model Relation: The weighted sum of features.

e.g. y = w1.x1 + w2.x2 + b



Epochs: Going through entire dataset is called one epoch.



Batch Gradient Descent:

1. We go through all training samples and calculate cumulative error.
2. Then we back propagate and adjust weights.



* Batch Gradient Descent uses all training samples for one forward pass and then adjust weights.
* Good for small training set.



Stochastic Gradient Descent(SGD):

* Uses one (randomly picked) sample for a forward pass and then adjust weights.
* Good when training set is very big and we don't want too much computation.



Mini Batch Gradient Descent:

* Uses a batch of (randomly picked) samples for a forward pass and then adjust weights.
* It is like SGD, instead of choosing one randomly picked training sample, you will use a batch of randomly picked training samples.



-----------------------------------------------------------------------------------------------------------------------------------------





Neural Network

--------------



1\. Neural networks, a model architecture designed to automatically identify nonlinear patterns in data, eliminating the need for manual feature cross experimentation.

2\. The fundamental(key) components of a deep neural network: nodes, hidden layers, and activation functions.

3\. The training process of neural networks involves the backpropagation algorithm to optimize predictions and minimize loss.

4\. Neural networks handle multi-class classification problems using: one-vs.-all and one-vs.-one approaches.



\# Neural networks are a family of model architectures designed to find nonlinear patterns in data. During training of a neural network, the model automatically learns the optimal feature crosses to perform on the input data to minimize loss.

