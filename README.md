
# Emotion Recognition and Facial Recognition Application

## Overview
This application is a web-based system designed for:
- **Facial Emotion Recognition**: Detecting and labeling emotions from facial images.
- **Facial Recognition**: Identifying users based on a pre-trained database of face encodings.
- **Live Camera Feed Integration**: Analyzing live camera feed for emotion and face recognition.

The application leverages Python libraries like Flask for the backend, TensorFlow and OpenCV for image processing and emotion detection. 

---

## Project Structure

### 1. Backend Python Scripts
- **`app.py`**: The main application script running the Flask server. Handles routing and integrates functionality for emotion recognition and facial recognition.
- **`emotion_recognition_app.py`**: Focuses on the emotion recognition part of the application, connecting a pre-trained ResNet50 model for emotion detection using the FERPlus dataset.
- **`emotion_recognition_start_stop.py`**: Provides start/stop functionality for the camera feed and manages real-time emotion detection.
- **`face_recognition_api.py`**: API endpoints for facial recognition functionalities such as user identification.
- **`Face_Recog_1_create_encodings.py`**: Script for generating face encodings from images in the dataset. Encodings are stored for later use.
- **`Face_Recog_2_train.py`**: Trains and fine-tunes the facial recognition model on the generated encodings.
- **`Face_Recog_3_webcam.py`**: Integrates webcam functionality for real-time face recognition.
- **`merged.py`**: Combines facial recognition and emotion detection capabilities for streamlined functionality.
- **`test.py`**: Utility script for testing individual components like emotion detection and face recognition.

### 2. Frontend
- **`index.html`**: The main webpage for interacting with the application. It includes sections for displaying live emotion and face recognition results.
- **`index_check.html`**: A secondary testing interface with similar functionalities.
- **`index.js`**: JavaScript for real-time updates and DOM manipulation, including live emotion results.
- **`index.css`**: Stylesheet for designing the frontend layout.

### 3. Data
- **`encoded-images-data.csv`**: Stores encoded data for facial recognition, linking user IDs to their respective face encodings.

---

## Features

### 1. Facial Emotion Recognition
- Uses a ResNet50 model trained on the FERPlus dataset.
- Detects seven emotions (e.g., happy, sad, angry) from images or live feed.
- Outputs mood percentages for multiple faces in the frame.

### 2. Facial Recognition
- Identifies users based on their face encodings stored in memory.
- Displays user-specific information on recognition.
- Notifies if a face is already in the system.

### 3. Real-time Camera Feed
- Provides a live video feed for emotion and face detection.
- Allows toggling the camera feed using start/stop controls.

---

## Installation

### Prerequisites
- Python 3.8 or above
- Required Python libraries: `Flask`, `OpenCV`, `TensorFlow`, `pandas`, `numpy`
- Compatible browser for accessing the web interface

### Steps
1. Clone the repository.
2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Generate face encodings:
   ```bash
   python Face_Recog_1_create_encodings.py
   ```
4. Train the recognition model:
   ```bash
   python Face_Recog_2_train.py
   ```
5. Start the application:
   ```bash
   flask run
   ```

---

## Usage

### Starting the Application
1. Run the `app.py` file.
2. Access the web interface at `http://127.0.0.1:5000/`.

### Web Interface
- **Live Feed**: Displays the camera feed with emotion and face detection overlays.
- **Start/Stop Camera**: Toggle the camera feed.
- **Emotion Results**: Shows live mood detection percentages.
- **Facial Recognition Results**: Identifies and displays recognized user details.

---

## Technologies Used

- **Backend**: Flask
- **Frontend**: HTML, CSS, JavaScript
- **Image Processing**: OpenCV
- **Model Training**: TensorFlow (ResNet50), pandas
- **Data Storage**: CSV for encodings

---

## Contribution
Feel free to modify and enhance the application. Contributions for new features like real-time analytics or improved model performance are welcome.

---

## Authors
Developed by Anshul Benhur Lakra and Piyush Kumar. 

--- 

## Notes
- Ensure your webcam is connected and functional for real-time feed analysis.
- The system's accuracy depends on the quality and size of the training dataset. Fine-tuning may be required for better performance.
