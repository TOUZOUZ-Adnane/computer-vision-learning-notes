

it is a positional encoding method for transformers that generates positional information dynamically based on local neighborhood context rather than using fixed position assignments

CPE encodes position implicitly through content, making transformers more robust to input size changes while preserving spatial locality 

# Core idea
Instead of adding a static position vector, CPE computes positional embeddings as a function of the input tokens themselves

# Why it exists

**Traditional positional encoding**
- Are resolution-dependent
- Break when input size changes
- Are weak for spatially structured data (images)

**CPE addressing this by making position**
- Content-aware
- Resolution-agnostic
- Locality-sensitive

# How it is implemented (common is vision)
- Tokens are reshaped into a 2D grid
- A depthwise convolution is applied
- Output is added back to tokens as positional information
This injects relative spatial structure without fixed indices