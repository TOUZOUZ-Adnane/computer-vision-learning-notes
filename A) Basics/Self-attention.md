
Self-attention is a mechanism that lets each element of an input (token, pixel, or patch) adaptively combine information from all other elements, based on relevance scores

# Core idea
For each token, self-attention answers:
	*Which other tokens should I pay attention to, and by how much?*  
![[self_attention.png|400]]

# Self-attention in vision
## Vision Transformers (ViT)
- Image -> split into patches
- Each patch = token
- Self-attention models global relationships between patches
## Hybrid models (e.g FastViT)
- Use convolutions in early stages
- Use self-attention only at low resolution

# Multi-head self-attention
Instead of one attention:
- Split channels into multiple heads
- Each head learns different relationships

# Why self-attention is powerful
- Captures long-range dependencies
- Content-adaptive
- Order-agnostic (with positional encoding)
- Strong scaling behavior


| Aspect              | Self-attention            | Convolution |
| ------------------- | ------------------------- | ----------- |
| Receptive field     | Global                    | Local       |
| Weights             | Dynamic (input-dependent) | Fixed       |
| Long-range modeling | Excellent                 | Weak        |
| Cost                | (O(N²))                   | (O(N))      |
# Takeaway
Self-attention lets each token dynamically gather information from all other tokens, enabling global context modeling at the cost of higher computation and memory