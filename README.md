# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file.
2. Display the video.
3. Display the video by resizing the window.
4. Rotate and display the video.

---

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook
- OpenCV (`cv2`)
- Matplotlib

---

## Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture a frame from the webcam and save it as a JPG image.

### Step 3:
Display the captured image using Matplotlib.

### Step 4:
Capture and display the live webcam video continuously.

### Step 5:
Resize the captured video frames and display them.

### Step 6:
Rotate the captured video frames by 90° clockwise and display them.

---

## Program

### Developed By:
**Name:** THARUN R

### Register No:
**212224240172**

---

### 1. Import the required libraries.

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```

---

### 2. Capture a frame from the webcam and save it as a JPG image.

```python
cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_frame.jpg", frame)

cap.release()
```

---

### 3. Read the captured image.

```python
captured_image = cv2.imread("captured_frame.jpg")
```

---

### 4. Display the captured image.

```python
plt.imshow(captured_image[:, :, ::-1])
plt.title("Captured Frame")
plt.axis("off")
plt.show()
```

---

### 5. Display the live webcam video.

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

### 6. Display the video after resizing.

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

### 7. Rotate the video by 90° clockwise and display it.

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)

    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

## Output

### i) Write the frame as JPG image
The captured frame is saved as **captured_frame.jpg**.

<img width="1280" height="720" alt="WIN_20260730_08_41_12_Pro" src="https://github.com/user-attachments/assets/f0628478-6d0a-4aa4-b40c-086ad6a92f02" />




### ii) Display the video
The live webcam video is displayed.

<img width="512" height="389" alt="d272cac6-f7ee-4b46-925d-f5bde2a0ac68" src="https://github.com/user-attachments/assets/7ed74d7b-3399-4ab1-b313-3a71286e0619" />



### iii) Display the video by resizing the window
The webcam video is displayed after resizing the frame.

<img width="512" height="389" alt="1c6c739d-40c0-42c8-bd5c-658a11eb4c7b" src="https://github.com/user-attachments/assets/c9bfc72e-c537-4d5c-801d-63c9d6c9c25c" />



### iv) Rotate and display the video
The webcam video is displayed after rotating it by **90° clockwise**.

<img width="297" height="389" alt="7bf0c226-18ce-47eb-8b3d-f183e3d93cb5" src="https://github.com/user-attachments/assets/e812c6c8-7ca7-48e1-9c3a-b4e3a8bdb8d4" />


## Result

Thus, the image was successfully captured from the webcam and various video processing operations such as image capture, live video display, resizing, and rotation were performed successfully using OpenCV.
