# Physics Informed Neural Network 
We employ neural networks with two hidden layers to analyze the data collected from a mapper, incorporating the Maxwell equations ∇·𝐵 = 0 and ∇×𝐵 = 0. The architecture of our neural network includes a first hidden layer with 48 units and a second hidden layer with 32 units. We use the ReLU activation function to introduce nonlinearity into the model, as it has proven to outperform other activation functions such as tanh and Swish in our tests. The learning rate for the training process is set to 1e-3
# inputs and outputs
we have 3 inputs(x, y,z ) at several locations, and output at corresponding locations are (Bx, By, Bz)
∇.𝐵, ∇×B
