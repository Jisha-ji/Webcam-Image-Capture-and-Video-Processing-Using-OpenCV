# EX NO:02 Image Capture and Video Processing Using OpenCV
## Name : JISHA BOSSNE SJ
## Register Number : 212224230106
---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program

### Developed By:
**Name:** JISHA BOSSNE SJ  

**Register No:** 212224230106

```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```
```
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
```
```
captured_image = cv2.imread('captured_frame.jpg')
```
```
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()

```
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

---

## Output

### i) Write the frame as JPG image
Captured image is saved as `Captured_Frame.jpg`

<img width="637" height="518" alt="image" src="https://github.com/user-attachments/assets/68589ad4-a6fd-4402-9efe-b4892113f92e" />

### ii) Display the video
Live webcam video is displayed

<img width="649" height="498" alt="image" src="https://github.com/user-attachments/assets/e266f104-d4d2-4a5d-8459-50f435eaeb77" />

### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)

<img width="338" height="489" alt="image" src="https://github.com/user-attachments/assets/9d91c4ba-feb6-41ba-a1f1-2102c3eb19d4" />

### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)

<img width="380" height="490" alt="image" src="https://github.com/user-attachments/assets/afdb0142-6f78-4fa4-b2db-c4ba20ffdd48" />

---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
