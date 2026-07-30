ASL translator

First part-Introduction:

The ASL Translator is a real-time American Sign Language (ASL) alphabet recognition system that uses computer vision and deep learning to recognize hand gestures from a webcam and translate them into text. The project is designed to run on an NVIDIA Jetson Orin Nano, enabling fast, on-device inference without requiring cloud services.
<img width="2190" height="1521" alt="Screenshot 2026-07-30 104448" src="https://github.com/user-attachments/assets/a55d671e-1f0d-4e04-aaaf-2c2a3ca2854d" />

Second part-The Algorithm:

This project uses a deep learning image classification model to recognize hand gestures representing the 26 letters of the American Sign Language alphabet.

How it Works

Image Capture 
A USB webcam connected to the NVIDIA Jetson Orin Nano continuously captures live video frames.

Image Preprocessing 
The input model expects the input frame with the resized dimensions. Data normalization so that the incoming images match the format used during model training.

Deep Learning Prediction 
The preprocessed image is fed into the trained neural network. The model predicts the ASL letter shown. The label with the highest associated confidence score is used as the prediction.

Display Results  
The predicted letter is overlaid on the video stream in real time. The loop repeats until the program is terminated.

Code Structure 
train.py is the file that trains the neural network using the ASL image dataset. 
inference.py loads the trained model and conducts real-time webcam predictions. The trained model can be found in the models/ folder. 
OpenCV provides the functionality for webcam access as well as processing images. In this project, the camera is connected by Python, which is also used in pre-processing images, running inference, and showing predictions.

Dependencies 
This project depends on the following libraries: Python 3; OpenCV; PyTorch(or TensorFlow, depending on your implementation); NumPy; NVIDIA JetPack (for Jetson devices)


Third part-Running This Project:

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
