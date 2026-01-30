
Knowledge distillation is a machine learning technique where a large, complex model (called the teacher) transfers what it has learned to a smaller, faster model (called the student). The goal is to keep most of the performance while reducing computation, memory use, and latency

# Core Idea
Instead of training the student on hard labels (this images is a cat), the student learns from the teacher's probability distribution across classes
This "soft" information tells the student that a cat looks somewhat like a dog, which improves generalization

# How it works
1) Train a large, high-accuracy teacher model
2) Run training data through the teacher to get soft predictions
3) Train the student using:
	- **Hard loss :** difference from true labels
	- **Distillation loss :** difference from teacher output
4) Deploy the smaller student model
Typical loss:
	*Loss = a.HardLoss + (1-a).DistillationLoss*

# Common Variation
- **Logit distillation :** match teacher probabilities 
- **Feature distillation :** mimic intermidiate representation
- **Self-distillation :** a model teaches a smaller version of it self
- **Online distillation :** teacher and student train together