# PyTorch
#math #python #programming #computer-science #deep-learning

PyTorch is a python library used to create and manage [[tensor|tensors]].

### Tensor Types
---
You can create a PyTorch tensor as different types such as `f16`, `f32`, `f64` or `int` .

```python
import torch


x = torch.ones(1, 2, dtype=int)
print(x)
print(x.dtype)
```

```bash
tensor([[1, 1]])
torch.int64
```

### CUDA Device
---
In PyTorch, you often want to have your calculations run on a tensor optimized device like a GPU or TPU. Since I have an Nvidia RTX 3070, it's of interest to specify that device be used in the PyTorch code for faster calculations.

```python

import torch

if torch.cuda.is_available():
    device = torch.device("cuda")
    x = torch.ones(5, device=device)
    print(x)
```

```bash
tensor([1., 1., 1., 1., 1.], device='cuda:0')
```

### Gradients
---

PyTorch tensors are often used with [[gradients]]. When instantiating a new tensor, if you define the `requires_grad` attribute, any future operational changes to that tensor will generate a gradient function as part of the output.

```python
import torch

x = torch.tensor([2., 3.], requires_grad=True)

print(x)

y = x+2
print(y)
```

```bash
tensor([2., 3.], requires_grad=True)
tensor([4., 5.], grad_fn=<AddBackward0>)
```

Running that gradient function will then generate and attach the gradient vector to the input tensors (via backpropogation).

```python
import torch

# Generate two tensors that require gradients
a = torch.tensor([2., 3.], requires_grad=True)
b = torch.tensor([6., 4.], requires_grad=True)

# Create a seprate tensor from a and b
y = 3*a**3 - b**2

# Calculate the gradients and store them on the tensor
external_grad = torch.tensor([1., 1.])
y.backward(gradient=external_grad)

# Print the new tensor and the gradient on the original tensors
print(y)
print(a.grad)
print(b.grad)
```

```shell
tensor([-12.,  65.], grad_fn=<SubBackward0>)
tensor([36., 81.])
tensor([-12.,  -8.])
```

## Training Loop
---

Using backpropogation on gradient-required input tensors in a loop allows us to train the 

