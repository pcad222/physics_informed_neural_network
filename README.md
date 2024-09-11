# Physics Informed Neural Network 
We employ neural networks with two hidden layers to analyze the data collected from a mapper, incorporating the Maxwell equations ∇·𝐵 = 0 and ∇×𝐵 = 0. The architecture of our neural network includes a first hidden layer with 48 units and a second hidden layer with 32 units. We use the ReLU activation function to introduce nonlinearity into the model, as it has proven to outperform other activation functions such as tanh and Swish in our tests. The learning rate for the training process is set to 1e-3

# inputs and outputs:
We have three input coordinates (x, y, z) at various locations, with corresponding magnetic field components( Bx, By, Bz)recorded at these  locations. Additionally, we include predefined cloudy points located within the upper and lower precession cells. Specifically, the x and y coordinates range from -25 cm to 25 cm, while the z coordinates vary from 5 cm to 15 cm for the upper cell and from -5 cm to -15 cm for the lower cell.The cloudy points are inside the precession cell only.

# loss
In the model we ∇·𝐵 = 0 and ∇×𝐵 = 0 and in terms of loss as loss= Loss = 𝜆_1 *mapper_mse_loss+ 𝜆_2* mean suared ∇.𝐵 + 𝜆_2* mean suared ∇x𝐵

Loss = 𝜆_1 (𝑦_𝑖−𝑦 ̂_𝑖)^2 + 𝜆_2 (<∇.𝐵^2>  >+𝜆_3 (<∇ 𝑋 𝐵)^2>

In the model, we apply the Maxwell equations:

∇⋅B = 0

and

∇×B = 0

The loss function is defined as:

Loss = λ₁ Loss_{mse_mapper} + (λ₁ Loss_{∇⋅B} + λ₂ Loss_{∇×B})

where:

Loss = λ₁ (∑ (yᵢ - ŷᵢ)²) + λ₂ (⟨∇⋅B⟩²) + λ₃ (⟨∇×B⟩²)



# Used Maxwell equations ∇·𝐵 = 0 and ∇×𝐵 = 0
