### Sports Celebrity Image Classification Project
This project implements an image classification system to identify sports celebrities using machine learning. It includes a Flask web server to handle image classification requests and a utility script for loading the model and processing images.

https://github.com/user-attachments/assets/2a307d43-705e-4a55-8157-2a58b2fdf726

## Project Structure
- server.py: This file contains the Python Flask server that serves the image classification functionality via a REST API.
- util.py: This file contains utility functions for image preprocessing, model loading, and the core classification logic.


## Features
1. Image Preprocessing:
    - Converts base64 encoded images to OpenCV images.
    - Detects faces and checks for the presence of two eyes using OpenCV's Haar cascades.
    - Extracts cropped face images for further processing.

2. Wavelet Transformation:
    - Applies wavelet transformation (w2d) to images to extract detailed features.

3. Machine Learning Model:
    - Uses a pre-trained machine learning model stored as saved_model.pkl for predicting the class of the sports celebrity.
    - Predicts both the class and the confidence probabilities for each image.

4. REST API:
    - The API allows users to send images (in base64 format) to the /classify_image endpoint, which returns the predicted sports celebrity's name, classification confidence, and the class dictionary.


## How to Run the Project
# Prerequisites
- Python 3.x
- Flask
- Joblib
- OpenCV
- Scikit-learn
- NumPy
  
# Steps to Run:
1. Clone or download the project files.
2. Install the required dependencies:
    - pip install flask numpy opencv-python scikit-learn joblib
3. Run the Flask server by executing:
    - python server.py
    The server will start on http://localhost:5000.
# API Usage:
- Endpoint: /classify_image
- Method: POST
- Request Body:
    - Send the image data in base64 format with the key image_data.

# Example of a POST request:
- curl -X POST http://localhost:5000/classify_image -F "image_data=<BASE64_IMAGE_STRING>"
  
# Testing:
You can test the classification using the predefined base64 test image for a famous sports personality (e.g., Virat Kohli) by calling the classify_image function directly from util.py.

## Model Artifacts
saved_model.pkl: This is the serialized model that is used for making predictions.
class_dictionary.json: This file contains the mappings between class numbers and sports celebrity names.
## Dependencies
- Flask: For building the web server.
- Joblib: For loading the machine learning model.
- OpenCV: For image processing, face detection, and eye detection.
- Scikit-learn: For model predictions and probabilities.
- NumPy: For array manipulation and handling image data.
## Acknowledgments
The wavelet transformation used in this project was adapted from an external source.
Pre-trained models and data processing techniques used are based on established machine learning practices.
