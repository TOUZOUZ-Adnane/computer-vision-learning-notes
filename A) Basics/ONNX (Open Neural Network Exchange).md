

ONNX is an open standard format for machine learning models. It allows models trained in one framework (PyTorch, TensorFlow) to be exported and run in another environment without rewriting the model

# What ONNX is
We can think of ONNX as universal language for AI models:
- Training frameworks each have their own internal representation
- ONNX converts that representation into a framework-agnostic computational graph
- Any runtime that supports ONNX can execute the model

# How ONNX works 

1) **Train the model**
You build and train the neural network in a framework like PyTorch

2) **Export to ONNX**
The framework converts (nodes = operations like Conv, ReLU)
- Graph structure (nodes = operations like Conv, ReLU)
- Tensors (weights)
- Metadata
```
Input -> Conv -> BatchNorm -> ReLU -> Output
```
Which becomes a standardized graph understood by ONNX tools

3) **Run with an inference engine**
A runtime such as ONNX Runtime loads the file and executes it efficiently on:
- CPU / GPU / Mobile devices / Edge hardware
The runtime applies optimizations like:
- Operator fusion / graph pruning / hardware acceleration

# What change between the pt and onnx

1) **Static Computational Graph**
Frameworks like PyTorch use dynamic graphs (built at runtime)
ONNX converts the model into a static graph:
- Operations are fixed ahead of time
- Shapes are often known
- Execution can be pre-planned
2) **Graph Optimizations**
Inferece engines such as ONNX Runtime modify the graph without changing the math
Typical optimizations:
-  Operator Fusion:
		``Conv + BatchNorm + ReLU`` becomes one fused kernel
- Why faster?
	- Fewer memory reads/writes
	- Fewer kernel launches on GPU
	- Better cache usage
Memory movement is often the real bottleneck, not raw computation

# Why it becomes faster 
Speed usually comes from execution efficiency, not from reducing model intelligence
Major contributors:
1) Operator fusion
2) Reduced memory movement
3) Static planning
4) Hardware-tuned kernels

# Why it becomes lighter
==ONNX does not automatically compress weights==
if the ``.onnx`` file is smaller, it usually because:
- Training artifacts were removed
- Parameters stored efficiency
- Optional graph simplification

# Key Insight
ONNX is not a model optimizer by itself
It is an optimization-friendly representation