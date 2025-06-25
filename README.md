<p align="center">
  <img src="public/images/Banner.png" alt="Sign Language Detection Banner" />
</p>



# Sign Language Detection (6th Sem Mini Project)

A computer vision project for real-time detection and classification of American Sign Language (ASL) alphabets and digits using a webcam, OpenCV, MediaPipe, and a Random Forest classifier.

## Features

- Collects hand gesture images for each sign class using your webcam.
- Extracts hand landmarks from images using MediaPipe.
- Trains a Random Forest classifier to recognize 36 classes (A-Z, 0-9).
- Real-time inference and visualization of detected signs.

## Project Structure

```
.
├── create_database.py
├── image_collect.py
├── inference_classifier.py
├── train_classifier.py
├── requirements.txt
├── .gitignore
├── README.md
├── data/                # Collected images (not tracked by git)
├── data.pickle          # Landmark dataset (generated)
├── model.p              # Trained model (generated)
```

## Setup

1. **Clone the repository** and navigate to the project directory.

2. **Install dependencies:**
   ```
   pip install -r requirements.txt
   ```

3. **Ensure you have a webcam connected.**

## Usage

### 1. Collect Images

Run the image collection script to capture images for each class:

```
python image_collect.py
```
- For each class, press `Q` to start capturing images.
- The script will save images in `./data/<class_id>/`.

### 2. Create Landmark Database

Extract hand landmarks from collected images and save them:

```
python create_database.py
```
- This generates `data.pickle` containing landmark features and labels.

### 3. Train the Classifier

Train a Random Forest model on the landmark data:

```
python train_classifier.py
```
- The trained model is saved as `model.p`.

### 4. Run Real-Time Inference

Start the real-time sign detection:

```
python inference_classifier.py
```
- Shows webcam feed with detected sign label.
- Press `Q` to quit.

## Notes

- The webcam index in the scripts is set to `1`. Change to `0` if your primary camera is at index 0.
- The project currently supports 36 classes: A-Z and 0-9.

## Requirements

- Python 3.7+
- OpenCV
- MediaPipe
- scikit-learn

See `requirements.txt` for details.

## Credits

- [MediaPipe](https://mediapipe.dev/) for hand landmark detection.
- [OpenCV](https://opencv.org/) for image processing.
- [scikit-learn](https://scikit-learn.org/) for machine learning.

---

*Developed as a mini project for the 6th semester.*
