

MobileOne is lightweight convolutional neural network backbone designed for ultra-fast inference on mobile and edge devices

![](<../Z) assets/mobileone.png>)
# Core idea
MobileOne uses structural re-parameterization:
- During training: multi-branch blocks improve optimization and accuracy
- During inference: all branches are fused into a single 3x3 convolution, hardware-friendly network

MobileOne is a backbone, not a full model. it is commonly used in:
- Image classification
- Object detection
- Semantic segmentation
- Pose estimation

Use MobileOne if:
- You target real-time mobile / edge deployment
- Latency is more important than peak accuracy
- You want simple inference graphs for hardware acceleration
