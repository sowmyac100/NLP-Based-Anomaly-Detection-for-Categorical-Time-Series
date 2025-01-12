# NLP-Based-Anomaly-Detection-for-Categorical-Time-Series
Data Preprocessing:

A synthetic dataset is created with categorical sensor readings. These are encoded into numerical values using LabelEncoder.
The dataset is then split into sequences of length 5 (using a sliding window), which serve as the input-output pairs for training the model.
Masked Word Prediction Model:

This model uses an embedding layer to convert the categorical sensor readings into dense vector representations (entity embeddings).
Three fully connected (dense) layers are used after the embedding to predict the next sensor value in the sequence.
Masked word prediction is done by setting a portion of the sensor readings to an invalid value (e.g., -1) and training the model to predict those masked values.
LSTM Model for Forecasting:

After training the masked word prediction model, the learned embeddings are used to train an LSTM model to predict the next sensor value in the sequence.
The LSTM model processes the embeddings and generates a forecast for the next time step.
Anomaly Detection:

The forecasting errors (the difference between the predicted and actual values) are used to detect anomalies.
A threshold based on the 95th percentile of the prediction errors is used to flag time steps as anomalies.

