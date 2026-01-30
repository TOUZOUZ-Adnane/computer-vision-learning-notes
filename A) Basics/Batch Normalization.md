
- Batch normalization is a technique used in neural networks to stabilize and speed up training by normalizing layer inputs during training
- Instead of letting activations drift as parameters change, BatchNorm keeps them well-behaved (roughly zero mean and unit variance)
# How it works
1) Compute batch statistics (mean and variance)
2) Normalize
3) Scale and shift (learnable)

# Why it helps
- Faster convergence (Allows higher learning rates)
- Stabilized gradients (reduces exploding/vanishing gradients)
- Regularization effect (Adds noise via statistics, sometimes reduces overfitting)

BatchNorm keeps each layer's inputs in a stable range, so every layer under consistent conditions as training progresses

there is other types of normalization
![[normalization_types.png]]

# BatchNorm
	For each channel (c), we minus it with its corresponding mean, which is calculated over the whole batch and all pixels

# LayerNorm
	For each example (n), we minus it with the corresponding mean, which is calculated over all channels and pixels

# InstanceNorm
	For each channel (c) and each example (n), we minus it with the corresponding mean

# GroupNorm
	This split a few channels into the same group, then we minus each group and each example with its corresponding mean