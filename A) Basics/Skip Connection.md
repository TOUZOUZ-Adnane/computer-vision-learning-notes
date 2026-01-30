
A skip connection (also called a shortcut connection) is a neural network design patters where the input of a layer is added or concatenated directly to the output of a later layer, bypassing one or more intermidiate layers
![[skip_connection.png | 600]]

# Why skip connections are used
- Mitigate vanishing gradients: Gradients can flow directly through the shortcut
- Enable very deep networks: Training remains stable even with hundreds of layers
- Improve convergence: Faster and more reliable training
- Preserve low-level features: Earlier representations are reused

# Common types
- **Additive skip connection :**
			y = F(x)+x
			used when dimensions match (ResNet)
- Concatenation skip connection:
			y = concat(F(x), x)
			used when combining features (encoder-decoder models)

Skip connections allow layers to refine features instead of relearning them from scratch. If a layer is not useful, the network can effectively learn the identity function and bypass it