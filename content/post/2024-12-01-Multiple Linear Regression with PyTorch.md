---
title: Multiple Linear Regression with PyTorch
author: sumendar
date: '2024-12-01'
slug: Python-Basics
categories: ['python', 'blogdown']
tags: ['basics']
subtitle: 'subtitle'
---


**Session Title: Multiple Linear Regression with PyTorch** 

---

**Objective** :
In this session, we will:

1. Build a **multiple linear regression model**  using PyTorch.

2. Use **sample data**  generated programmatically.

3. Explain **each line of code**  in detail.

4. Understand the real-world relevance of multiple linear regression.


---

**1. What is Multiple Linear Regression?** **Theory** : 
- **Multiple Linear Regression**  predicts a target variable ($$y$$) based on multiple independent variables ($$x_1, x_2, \ldots, x_n$$).

- The relationship is defined as:
$$
 y = w_1x_1 + w_2x_2 + \ldots + w_nx_n + b 
$$

where: 
  - $$w_i$$: Weights for each feature.

  - $$b$$: Bias (intercept).

  - $$y$$: Target variable.
**Real-World Example** : 
- Predicting **monthly rent**  ($$y$$) of a house based on: 
  - **Size (sq ft)**  ($$x_1$$).

  - **Number of bedrooms**  ($$x_2$$).

  - **Distance to city center**  ($$x_3$$).


---

**2. sample Data Generation** We’ll create a dataset with three features ($$x_1, x_2, x_3$$) and a target ($$y$$) using the formula:
$$
 y = 3x_1 + 2x_2 - x_3 + \text{noise} 
$$


---



```python
import torch
import torch.nn as nn
import numpy as np
import matplotlib.pyplot as plt

# Hyper-parameters
input_size = 3  # Three independent variables
output_size = 1  # One target variable
num_epochs = 100
learning_rate = 0.01

# Generate sampledata
np.random.seed(42)
x_train = np.random.rand(100, 3) * 10  # 100 samples, 3 features
weights = np.array([3.0, 2.0, -1.0])  # True weights
bias = 5.0  # True bias
noise = np.random.randn(100, 1)  # Add some noise

# Calculate y using the linear relationship
y_train = np.dot(x_train, weights.reshape(-1, 1)) + bias + noise
```
**Code Explanation** : 
1. **Input Data**  ($$ x$$): 
  - `x_train`: 100 samples with 3 features each, randomly generated.

  - Example: A single row might represent a house with:
    - Size = 6.2 sq ft.

    - Bedrooms = 3.

    - Distance = 8.1 km.

2. **True Weights and Bias** : 
  - `weights`: The actual relationship between features and the target. 
    - Size contributes positively ($$+3x_1$$).

    - Bedrooms contribute positively ($$+2x_2$$).

    - Distance contributes negatively ($$-x_3$$).

  - `bias`: A fixed base value for all predictions.

3. **Noise** :
  - Adds randomness to simulate real-world data.

4. **Target Variable ($y$)** :
  - Combines features, weights, bias, and noise to generate realistic predictions.


---

**3. Building the Model** **Model Definition** :

```python
# Define the linear regression model
model = nn.Linear(input_size, output_size)
```

- **Why a Linear Model?** 
  - We are solving a linear regression problem, where the relationship between inputs and outputs is linear.

- **What Does `nn.Linear` Do?**  
  - Creates a linear layer with: 
    - `input_size` = 3 (three features).

    - `output_size` = 1 (one predicted value).


---

**4. Define Loss Function and Optimizer** **Loss Function** :

```python
criterion = nn.MSELoss()
```

- **Why MSE?** 
  - Measures the average squared difference between predicted and actual values.

  - Smaller MSE = Better predictions.
  **Optimizer** :

```python
optimizer = torch.optim.SGD(model.parameters(), lr=learning_rate)
```

- **Why SGD?** 
  - Adjusts weights based on the gradient of the loss function with respect to each weight.

  - `lr=0.01`: Controls how big each adjustment step is.


---

**5. Training the Model** **Training Loop** :

```python
for epoch in range(num_epochs):
    # Convert numpy arrays to torch tensors
    inputs = torch.from_numpy(x_train).float()
    targets = torch.from_numpy(y_train).float()
    
    # Forward pass: Compute predictions
    outputs = model(inputs)
    loss = criterion(outputs, targets)
    
    # Backward pass: Compute gradients
    optimizer.zero_grad()
    loss.backward()
    optimizer.step()
    
    if (epoch + 1) % 10 == 0:
        print(f"Epoch [{epoch+1}/{num_epochs}], Loss: {loss.item():.4f}")
```
**Line-by-Line Explanation** : 
1. **Convert Data to Tensors** : 
  - PyTorch works with `torch.Tensor` objects, not `numpy`.

  - `.float()`: Ensures the data is in floating-point format.

2. **Forward Pass** : 
  - `outputs = model(inputs)`: Feeds inputs through the model to get predictions.

3. **Calculate Loss** : 
  - `loss = criterion(outputs, targets)`: Compares predictions (`outputs`) to actual values (`targets`).

4. **Backward Pass** : 
  - `optimizer.zero_grad()`: Clears old gradients.

  - `loss.backward()`: Calculates gradients for all weights and bias.

5. **Update Weights** : 
  - `optimizer.step()`: Adjusts weights and bias to minimize loss.

6. **Monitor Training** :
  - Prints the loss every 10 epochs to track progress.


---

**6. Visualizing Results** **Plot the True vs. Predicted Values** 

```python
# Evaluate the model
model.eval()
predicted = model(torch.from_numpy(x_train).float()).detach().numpy()

# Visualization
plt.figure(figsize=(10, 6))
plt.scatter(range(len(y_train)), y_train, color='blue', label='True Values')
plt.scatter(range(len(predicted)), predicted, color='red', label='Predicted Values')
plt.title('True vs Predicted Values')
plt.xlabel('Sample Index')
plt.ylabel('Target Value')
plt.legend()
plt.show()
```
**Explanation** : 
1. `model.eval()`: Switches the model to evaluation mode (disables gradient calculations).

2. `detach()`: Prevents tracking gradients for predictions (not needed during testing).

3. **Plot** :
  - Blue dots: Actual values.

  - Red dots: Predicted values.


---

**7. Saving the Model** 

```python
torch.save(model.state_dict(), 'multiple_linear_regression.ckpt')
```

- Saves the trained weights and bias for later use.


---

**Complete Code** 

```python
import torch
import torch.nn as nn
import numpy as np
import matplotlib.pyplot as plt

# Hyper-parameters
input_size = 3
output_size = 1
num_epochs = 100
learning_rate = 0.01

# Generate sampledata
np.random.seed(42)
x_train = np.random.rand(100, 3) * 10
weights = np.array([3.0, 2.0, -1.0])
bias = 5.0
noise = np.random.randn(100, 1)
y_train = np.dot(x_train, weights.reshape(-1, 1)) + bias + noise

# Linear regression model
model = nn.Linear(input_size, output_size)

# Loss and optimizer
criterion = nn.MSELoss()
optimizer = torch.optim.SGD(model.parameters(), lr=learning_rate)

# Train the model
for epoch in range(num_epochs):
    inputs = torch.from_numpy(x_train).float()
    targets = torch.from_numpy(y_train).float()
    
    outputs = model(inputs)
    loss = criterion(outputs, targets)
    
    optimizer.zero_grad()
    loss.backward()
    optimizer.step()
    
    if (epoch + 1) % 10 == 0:
        print(f"Epoch [{epoch+1}/{num_epochs}], Loss: {loss.item():.4f}")

# Visualize results
model.eval()
predicted = model(torch.from_numpy(x_train).float()).detach().numpy()
plt.figure(figsize=(10, 6))
plt.scatter(range(len(y_train)), y_train, color='blue', label='True Values')
plt.scatter(range(len(predicted)), predicted, color='red', label='Predicted Values')
plt.title('True vs Predicted Values')
plt.xlabel('Sample Index')
plt.ylabel('Target Value')
plt.legend()
plt.show()

# Save the model
torch.save(model.state_dict(), 'multiple_linear_regression.ckpt')
```


---

**Learning Outcomes**  
1. **Understand multiple linear regression**  and how to implement it in PyTorch.

2. Learn to **generate sample data**  for experimentation.

3. Visualize **true vs. predicted values**  to evaluate model performance.

![](https://i.postimg.cc/jdXdbmNn/napkin-selection-1.png)