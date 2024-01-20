# codealpha-task1.ml.khushiNayak
This Python code is a simple real-time facial expression recognition system using a pre-trained deep learning model. Let's break down the code step by step:

Importing Libraries:

cv2: OpenCV library for computer vision tasks.
model_from_json: Function to create a Keras model from a JSON file.
numpy: Library for numerical operations.
Loading the Pre-trained Model:

It loads a pre-trained facial expression recognition model from a JSON file (facialemotionmodel.json) and its weights from an H5 file (facialemotionmodel.h5).
The model architecture is stored in the JSON file, and the weights are stored in the H5 file.
Loading Haar Cascade for Face Detection:

Haar cascade classifier for face detection is loaded from the OpenCV data directory.
Defining a Function to Extract Features:

extract_features is a function that takes an image and converts it into a numpy array. It reshapes the array to match the input shape expected by the model and normalizes the pixel values.
Initializing Webcam and Labels:

webcam is initialized using OpenCV to capture video from the default camera (camera index 0).
labels is a dictionary mapping emotion indices to emotion labels.
Real-time Face Detection and Expression Recognition:

Inside an infinite loop (while True), frames are captured from the webcam.
Each frame is converted to grayscale.
The detectMultiScale function from OpenCV is used to detect faces in the frame.
For each detected face, the code extracts the face region, resizes it to 48x48 pixels (the input size expected by the model), and normalizes the pixel values.
The pre-trained model predicts the emotion label for the face.
The predicted label is then overlaid on the video frame using OpenCV's putText function.
The processed frame is displayed in a window named "Output."
The loop continues until the user presses the 'Esc' key (key code 27).
Exception Handling:

There is a try-except block to handle potential errors during face detection. If there is an error (e.g., no faces detected), it is caught and ignored.
Exiting the Program:

The program can be terminated by pressing the 'Esc' key (cv2.waitKey(27)).
Overall, this code provides a simple real-time facial expression recognition system using a pre-trained deep learning model and face detection with OpenCV. The model predicts the emotion labels, and the results are displayed on the video feed in real-time.
