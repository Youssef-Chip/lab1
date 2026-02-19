# Motivation
The motivation for using the Human Activity Recognition Using Smartphones dataset from the UCI repository is to learn and gain experience with making predictions on time series data. The nature of the data requires a knowledge of previous actions as well as considering windows of data. For example, I could look at the last 7 seconds of activity to determine what is happening at the 7th second. If the data was given to the model in random order, it would not be able to make sense of the x, y, and z coordinates recorded by the phone. The nature of the data makes feature engineering a crucial step to obtaining high accuracy.


# Target Definition
The target is to be able to classify 1 of 6 activities. These include whether a person walking, walking upstairs, walking downstairs, sitting, standing, or laying. I.e. given the data, we must create a model that is capable of multi-classification on time horizon data. 


# Data Sources/license
The dataset comes from the UCI Repository and is under the Creative Commons Attribution 4.0 International (CC BY 4.0) license. It was a study conducted by Jorge Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto ,Xavier Parra. They had a group of 30 volunteers within ages 19-48 and each person performed the previously mentioned activities while wearing a smartphone on their waist.


# Signal Description
The data is composed of accelerometer and gryoscope sensor signals which captures 3 axes of linear acceleration and 3 axes of angular velocity at a constant rate of 50Hz (50 snapshots per second). Linear acceleration measures how fast the device is speeding up or slowing down, while angular velocity measures how fast the device is rotating around those axes.

These signals were preprocessed by applying noise filters and then sampled in sliding windows of 2.56 seconds with a 50% overlap. The acceleration signal has gravitational and body motion components. These were separated using a Butterworth low-pass filter which smooths out jitteriness, reduces variance, and cuts off frequencies that are too high. The creators assume the gravitational force has only low frequency components, so a filter with 0.3 Hz cutoff frequency was used.


# Limitations/Risks
The study has a few limitations, including but not limited to controlled environment, demographic bias, simplicity of the activities. Some risks are that a person may be reidentified through patters in the data that are unique to them and the model may overfit and not be acurrate in real world scenarios, where false negatives or positives may cause some risk. 