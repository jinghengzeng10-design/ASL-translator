ASL translator

Introduction

The ASL Translator is a real-time American Sign Language (ASL) alphabet recognition system that uses computer vision and deep learning to recognize hand gestures from a webcam and translate them into text. The project is designed to run on an NVIDIA Jetson Orin Nano, enabling fast, on-device inference without requiring cloud services.
<img width="2191" height="1572" alt="Screenshot 2026-07-30 101300" src="https://github.com/user-attachments/assets/85be5b58-2089-4d35-9dfc-953e45eaeb67" />

The Algorithm

This project uses a deep learning image classification model to recognize hand gestures representing the 26 letters of the American Sign Language alphabet.

How it Works

Image Capture
A USB webcam connected to the NVIDIA Jetson Orin Nano continuously captures live video frames.

Image Preprocessing
Each frame is resized to the input size expected by the trained model.
Images are normalized so they match the format used during training.

Deep Learning Prediction
The preprocessed image is passed into the trained neural network.
The model predicts which ASL letter is being shown.
The class with the highest confidence score is selected as the prediction.

Display Results
The predicted letter is displayed on the video stream in real time.
The process repeats continuously until the program is closed.

Code Structure
train.py trains the neural network using the ASL image dataset.
inference.py loads the trained model and performs live webcam prediction.
The trained model is stored in the models/ directory.
OpenCV is used for webcam access and image processing.
Python is used to connect the camera, preprocess images, run inference, and display predictions.

Dependencies
This project depends on the following libraries:
Python 3
OpenCV
PyTorch (or TensorFlow, depending on your implementation)
NumPy
NVIDIA JetPack (for Jetson devices)

Running This Project

1. Clone the Repository
git clone https://github.com/jinghengzeng10-design/ASL-translator.git
cd ASL-translator

2. Install Required Libraries
pip3 install -r requirements.txt
If you do not have a requirements.txt file, install the required packages manually:
pip3 install opencv-python numpy torch torchvision
(If you are using TensorFlow instead of PyTorch, replace the PyTorch packages with TensorFlow.)

3. Connect the Webcam
Connect a USB webcam to the NVIDIA Jetson Orin Nano and verify that it is detected.

4. Run the Translator
python3 inference.py
The webcam window will open and begin recognizing ASL alphabet gestures in real time. The predicted letter will appear on the screen as you perform each sign.

Video Demonstration
View a video explanation here
