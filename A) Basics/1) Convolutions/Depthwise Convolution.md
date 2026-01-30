

Depthwise convolution is a type of convolution that applies ==one spatial filter per input channel==, instead of mixing all channels together as in standard convolution
![[depthwise_convolution.png]]

# Depthwise separable convolution
Depthwise convolution is almost always used with pointwise convolution (1x1):
1) Depthwise conv -> spatial filtering (per channel)   ==Where is the feature==
2) Pointwise conv (1x1) -> channel mixing  ==Which features should interact==
much cheaper than standard convolution

![[depthwise_pointwise_convolution.png|400]]

# Where it is used
- Mobile and embedded models
- Real-time vision systems
- Architectures like MobileNet, EfficientNet, Eception