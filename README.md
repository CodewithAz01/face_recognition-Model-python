# Face_recognition-Model-python
How to setup the face recognition model on python

# Step 1
Install the cmake version related to the python version i use 3.8 python so i install cmake 3.26.3 which is capable with my python version the cmake setup will be given in the repository

<a href="https://drive.google.com/file/d/1_s8VNyPiCCy5XFm799_xeVZH476UhDcF/view?usp=drive_link">
    <img src="https://img.shields.io/badge/Download-Project-blue?style=for-the-badge" alt="Download Cmake">
</a>

# Step 2 
Install the dlib wheel in the python packages using 
<br><b>pip install (Path of the file).</b> 
<br>"Dlib wheel will be given the repository"

# Step 3 
Install face recognition model using 
<br><b>pip install face-recongnition</b>

# Test the Model Face Detection Using face_recognition and OpenCV

This script detects faces in an image using the `face_recognition` library and displays the image with green bounding boxes around detected faces.

## Requirements

Install the required packages:

```bash
pip install face_recognition opencv-python
```

## Python Code

```python
import face_recognition
import cv2

# Load image
image = face_recognition.load_image_file("download (8).jpg")

# Detect faces
face_locations = face_recognition.face_locations(image)

print(f"Found {len(face_locations)} face(s).")

# Convert RGB image to BGR for OpenCV
image_bgr = cv2.cvtColor(image, cv2.COLOR_RGB2BGR)

# Draw bounding boxes around detected faces
for (top, right, bottom, left) in face_locations:
    cv2.rectangle(
        image_bgr,
        (left, top),
        (right, bottom),
        (0, 255, 0),  # Green color
        2             # Line thickness
    )

# Display image
cv2.imshow("Face Detection Test", image_bgr)

print("Press any key to close the window...")
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output
<p align="center">
  <img src="img/Screenshot 2026-06-01 225016.png" alt="Face Detection Result" width="70%">
</p>

```text
- Detects all faces in the image.
- Draws a green bounding box around each detected face.
- Opens a window showing the detection results.
- Prints the total number of faces found.
```

### Example Output

```text
Found 3 face(s).
Press any key to close the window...
```
