# Deep_Audio_Classifier
This project classifies Capuchinbird calls from audio recordings using TensorFlow and TensorFlow I/O. It handles audio preprocessing, including resampling and converting audio into spectrograms. The model is trained to differentiate between Capuchinbird calls and background noise, aiming to predict bird calls in long-duration forest recordings.

Project Overview
The project is divided into the following steps:

Import and Install Dependencies:

Installing TensorFlow and TensorFlow I/O to handle audio processing.
Build Data Loading Functions:

Functions to load .wav files, resample them to 16kHz, and extract necessary audio features.
Dataset Preparation:

Loading positive and negative audio samples (Capuchinbird vs. Not Capuchinbird).
Calculate Call Length:

Determine the average length of Capuchinbird calls from the dataset.
Preprocessing:

Convert audio files into spectrograms using Short-Time Fourier Transform (STFT) to visualize the frequency content.
Model Building:

A Convolutional Neural Network (CNN) is constructed to classify audio spectrograms. It consists of convolution layers and a fully connected layer to perform binary classification.
Training and Evaluation:

The model is trained on the Capuchinbird dataset and validated using separate test data.
Prediction:

Predictions are made on unseen forest recordings, followed by grouping consecutive predictions to identify distinct Capuchinbird calls.
Exporting Results:

The final predictions (bird calls per audio file) are exported into a CSV file for further analysis.
Installation
Ensure you have the required dependencies by running the following commands:

bash
Copy code
!pip install tensorflow
!pip install tensorflow_io
How to Run
Clone this repository.
Load the project into Google Colab or any Jupyter environment.
Ensure that your audio files are in the correct format and path.
Execute the cells step-by-step to train the model and make predictions.
Dataset
Positive samples: Capuchinbird calls (parsed into clips).
Negative samples: Background noise or other bird calls.
Model Details
The model is a simple Convolutional Neural Network (CNN) with:

Conv2D layers to extract spatial features from spectrograms.
Flatten and Dense layers for classification.
Binary cross-entropy loss and Adam optimizer for model training.
Results
The model classifies audio files based on the presence of Capuchinbird calls. The number of calls in each recording is saved in a CSV file.
