

Overparameterization means using more parameters than strictly necessary to represent a function, typically during training, to make optimization easier and improve accuracy

# Core idea
Train a larger and more expensive model, then:
- Either keep it (classical overparameterization), or
- Compress it at inference (modern train-time overparameterization)

# Why overparameterization helps training
1) Easier optimization
	- Loss landscape becomes smoother
	- Fewer bad local minima
	- Gradients flow better
2) Better representational capacity
	- Can represent complex functions
	- Learns richer intermediate features
3) Implicit regularization
	- SGD trends to find simple solutions even in large models
This is why modern deep networks are often heavily overparameterized yet generalize well


# Classical VS train-time overparameterization
**Classical overparameterization**
- Large model
- Large inference cost
**Train-time overparameterization**
- Extra parameters only during training
- Parameters are merged (reparameterized) before inference
- Inference model is small and fast

# Key takeaway
- Overparameterization = extra capacity to help training
- Modern efficient models use it only during training
- Final deployed model is small, fast and clean
- Strongly linked to structural reparameterization