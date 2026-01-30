
A Vision Language model is a multimodal model trained to jointly understand images and natural language. Unlike classic computer vision models (CNNs, ViTs) that output labels or embeddings, VLMs learn a shared representation space between visual and textual data.

![[VLM.jpeg]]
# In short:
- Vision -> pixels / patches
- Language -> tokens
- VLM -> aligned semantic space


# Core idea (why VLMs work)

VLMs are trained on large-scale image-text pairs (image + caption)
The training objective encourages:
- relevant images <-> relevant text to be close
- irrelevant image-text pairs to be far apart
This alignment enables zero-shot and open-vocabulary reasoning

# Typical architecture

Most VLMs follow this pattern:
1) Vision encoder
	- CNN or ViT
	- Outputs image embeddings
2) Text encoder
	- Transformer-based
	- Outputs text embeddings
3) Alignment head
	- Contrastive loss or cross-attention
**Some models use dual encoders, others a single multimodal transformer**

# What VLMs can do

- Zero-shot image classification
- Image-text retrieval
- Visual Question Answering (VQA)
- Image captioning
- Grounded reasoning (what is where and why)

# Why VLMs matter for CV 
compared to classic supervised CV:
- No fixed label space
- Better generalization
- Natural language supervision
- Easier task adaption via prompts
This shift CV from:
	*predict labels -> understand semantics*

# Limitations
- weak at fine-grained localization (unless combined with detectors)
- Sensitive to prompt wording
- Learn dataset biases from web-scale data
- Often lack explicit spatial reasoning

# How VLMs integrate with modern systems
Common pipelines:
- VLM + Detector (grounding objects via text)
- VLM + LLM (reasoning over visual content)
- VLM as feature extractor (downstream CV tasks)
This is the foundation of multimodal AI agents