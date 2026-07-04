Face Detection App

A real-time face detection app using the Viola-Jones algorithm (Haar Cascade classifier), built with OpenCV and deployed via Streamlit.

Overview

This app detects faces in a live webcam feed using the classic Viola-Jones face detection method, implemented via OpenCV's pre-trained Haar Cascade classifier. It provides an interactive interface where users can adjust detection parameters in real time and see the effect on how faces are detected.

Features


Live webcam-based face detection using OpenCV
Interactive sliders to adjust detection sensitivity:

Min Neighbours (range 1–10, default 5) — controls how many neighboring rectangles are required to retain a detected face candidate
Scale Factor (range 0.0–3.0, default 1.3) — controls how much the image size is reduced at each scale during detection



Minimum face size fixed at 30x30 pixels to filter out very small false detections
Built-in usage instructions accessible via a button in the app
Draws bounding boxes around detected faces in the live video feed
Exits cleanly when the "q" key is pressed


Tech Stack


Python
OpenCV (cv2) — Haar Cascade face detection, webcam capture, image processing
Streamlit — web app interface and interactive controls


Project Structure

facial-detection-app/
├── facial.py                                  # Streamlit app

├── haarcascade_frontalface_default .xml       # Pre-trained Haar Cascade classifier

├── facial.png                                  # App image/banner

├── requirements.txt                             # Project dependencies


How to Run Locally

bash# Clone the repository
git clone https://github.com/Osabhue-Mathew24/facial-detection-app.git
cd facial-detection-app

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run facial.py

Note: This app accesses your device's webcam directly via OpenCV (cv2.VideoCapture(0)), so it needs to be run in an environment with local webcam access — it will not work as-is in a cloud-hosted Streamlit deployment without modification.


How It Works


The app loads a pre-trained Haar Cascade classifier (haarcascade_frontalface_default.xml) for frontal face detection
The user can adjust two detection parameters via sliders: Min Neighbours and Scale Factor
On clicking "FACE DETECT," the webcam feed opens and each frame is converted to grayscale
The Haar Cascade classifier scans each grayscale frame for face-like patterns based on the selected parameters
Detected faces are outlined with bounding boxes drawn directly on the live video feed
The detection loop runs continuously until the user presses "q" to exit


Future Improvements


Add support for image/video file uploads, not just live webcam feed, so it can run in cloud deployments
Display the number of faces detected in real time within the Streamlit UI itself (currently shown via a separate OpenCV window)
Experiment with more modern face detection methods (e.g., a CNN-based detector) and compare accuracy/speed against Haar Cascade
Add face count or confidence overlay directly on the Streamlit interface


Author

Matthew Osabhue Iyasele


Email: mathewiyasele@gmail.com

