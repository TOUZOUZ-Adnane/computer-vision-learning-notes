
A dence convolution (usually called standard convolution) is the regular convolution used in CNNs where every output channel is connected to all input channels

# Why we name it dence convolution
Because the connectivity between input and output channels is fully dence (no channel sparsity)

# Why dense convs are still important
Despite their cost, dense convolutions:
- Mix spatial and channel information simultaneously
- Often give higher accuracy
This is why efficient models (MobileNet, FastVit, ConvNeXt)
- Replace dence convs at inference
- But use dense structure during training via overparameterization
- Then reparameterize back to a single dense conv