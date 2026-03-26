# Model Details
Developers: Darwin, Youssef, Munzir. RPI Spring 2026

Model Date: March 26, 2026

Model Type: google/vit-base-patch16-224 (Transformer) and microsoft/resnet-50 (CNN)

Framework: Huggingface, Pytorch

# Intended Use
Primary Application: General image classification used here to identify medical Personal Protective Equipment (PPE).

Target: Designed for classifying images into 1,000 everyday object categories (ImageNet).

Out-of-scope use: These models are not specialized for medical diagnostics or high-stakes safety compliance. They should not be used as a primary tool for identifying medical gear in a clinical setting without further fine-tuning.

# Evaluation Data
Source: huggingface cppe-5 dataset.

Split Strategy: Selected the first 20 images from the training set to evaluate latency and qualitative performance on specialized medical gear.

# Quantitative Analyses
The ResNet-50 (CNN) model demonstrated significantly higher efficiency, with an average latency of 53.30 ms per image. In contrast, the ViT (Transformer) model was more than twice as slow, with an average latency of 118.73 ms.

While both models were pushed outside of their original training domain, the ViT model showed a higher confidence in relevant PPE-related categories (e.g., 54.8% for gasmask) compared to the ResNet-50, which struggled more with the specialized visual data (Top prediction: "snorkel" at 40.4%).

# Ethical Considerations & Limitations
As these models are pre-trained on large-scale public datasets (ImageNet), they may carry inherent biases regarding how certain objects or environments are represented. Users should be aware that the models might "hallucinate" everyday labels onto specialized equipment.

# Failure
Both models are prone to domain-shift failure. Since neither was specifically trained on the cppe-5 medical labels, they often map medical gear to the nearest "everyday" visual match (like labeling a mask as a "snorkel" or "ski mask"). To improve accuracy, the models would require fine-tuning on labeled medical datasets rather than relying on zero-shot or general-purpose classification.