
it is a neural network layer where every input neuron is connected to every output neuron via learnable weight

Each output unit depends on all input features, unlike convolution layers which connect locally

![[fc_layer.png|400]]
# Where it is used
- Classification heads (mapping features -> class scores)
- Regression outputs
- MLPs (multi-layer perceptron)
- Final layers of CNNs and Vision Transformers

# Key properties
- High expressive power
- Parameter-heavy
- Prone to overfitting if overused
- Not spatially aware