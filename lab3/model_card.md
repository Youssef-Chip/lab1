Model Card: Sentiment Analysis with Bert and Roberta

# Model Details
Developers: Darwin, Youssef, Munzir. RPI Spring 2026\
Model Data: March 19, 2026\
Model Type: lvwerra/distilbert-imdb and siebert/sentiment-roberta-large-english\
Framework: Huggingface, Pytorch

# Intended Use
Primary Application: Sentiment analysis on imbd movie reviews.

Target: Designed for overall sentiment analysis on any string.

Out-of-scope use: Does not work for robust text classification problems, or named entity recongnition. The models only outputs positive or negative sentiment.

# Evaluation Data
Source: huggingface imdb dataset

Split Strategy: Shuffled the dataset and selected 200 at random

# Quantitative Analyses

The fine tuned distiBert model got lower accuracy then the bigger roberta model, however the Roberta model has many more parameters so it takes around 5 times longer to compute. The results demonstrate how performance may be sacrificed for small a improvement.

# Ethical Considerations & Limitations

It is hard to reverse engineer the identity of the user, as long as they do not reveal personal information in the training data.

# Failure

When one of the input has more tokens then what the model is prepared to take in, the pipeline fails. To fix this, truncate the input tokens if needed before running inference.