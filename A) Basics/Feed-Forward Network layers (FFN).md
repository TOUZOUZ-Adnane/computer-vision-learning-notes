
FFN layers are per-token neural networks used inside Transformers and hybrid vision models to expand, transform, and compress feature representation after token mixing

ConvFFN performs channel-wise transformation and feature refinement after spatial mixing

# Purpose of FFN layers
1) **Channel mixing**
	- [[Self-attention]] mixes tokens
	- FFN mixes channels
2) **Non-linearity**
	- Adds expressive power
	- Enable complex feature transformations
3) **Capacity expansion**
	- Temporarily increases dimensionality
	- Improves representation learning

# FFN layers in vision models
## Vision Transformers (ViT)
- FFN = two Linear layers
- Operates on patch tokens
## CNN / hybrid models
- FFN = 1x1 conv -> activation -> 1x1 conv
- Sometimes includes depthwise convolution for spatial context