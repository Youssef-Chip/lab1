Model Card: HAR Sequence Classifier (GRU/LSTM)

# Model Details
Developers: Darwin, Youssef, Munzir. RPI Spring 2026\
Model Data: March 12, 2026\
Model Type: LSTM/GRU (Recurrent Neural Network)\
Framework: PyTorch / TensorFlow

# Intended Use
Primary Application: Real-time recognition of 6 physical activities (Walking, Walking_Upstairs, Walking_Downstairs, Sitting, Standing, Laying) using smartphone-based Inertial Measurement Unit (IMU) data.

Target Device: Designed for on-device deployment (e.g., mobile apps) and low-latency inference is required.\
Target Users: Individuals using fitness tracking or health monitoring applications.

Out-of-scope use: Phone placed anywhere that is not the waist. The gyroscope depends on the rotation of the phone representing the rotation of the full body.

# Evaluation Data
Source: UCI Human Activity Recognition (HAR) dataset.

Split Strategy: Subject-disjoint split (Subjects 1-21 for training, 22-30 for testing).

Signal Info: 9-channel inertial signals (Acc/Gyro), windowed at 2.56 seconds.

# Quantitative Analyses

The model achieved a final Test Macro-F1 score of 89%. Evaluation via confusion matrix revealed that the model excels at distinguishing dynamic activities (Walking vs. Laying) but exhibits a 83% and 80% F1 score between "Sitting" and "Standing." This is most likely caused by the similarity in gravitational vectors when the device is stationary.

# Ethical Considerations & Limitations

To preserve user privacy, this model is designed for local, on-device inference to avoid transmitting biometric gait signatures. A significant limitation is the demographic bias of the training set (adults aged 19–48); therefore, the model’s reliability for pediatric or geriatric populations is unverified and potentially lower.