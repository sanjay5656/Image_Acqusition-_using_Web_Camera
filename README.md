# Image_Acqusition-_using_Web_Camera
## Aim

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import OpenCV Package.

### Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.

### Step 3:
Read Video or Image. Utilize 'imread' to read a video frame or image from the webcam.

### Step 4:
Save Image to File. Employ 'imwrite' to save the captured image to a file.

### Step 5:
Display Video or Image. Use 'imshow' to display the captured video frame or image, and end Program with 'q'. Allow the program to be terminated by pressing the 'q' key.

## Program:

### Developed By : Sanjay S
### Register No  : 212221243002

## i) Write the frame as JPG file
```python
videoCaptureObject = cv2.VideoCapture(0)
max_frames = 4  # Maximum number of frames to capture
frame_count = 0

while frame_count < max_frames:
    ret, frame = videoCaptureObject.read()
    cv2.imwrite(f"img_{frame_count}.jpeg", frame)
    frame_count += 1

videoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window
```python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image
![IMG-20240305-WA0005](https://github.com/sanjay5656/Image_Acqusition-_using_Web_Camera/assets/115128955/4816fee9-cbb5-481e-bae4-dbc809146b24)

### ii) Display the video
![IMG-20240305-WA0007](https://github.com/sanjay5656/Image_Acqusition-_using_Web_Camera/assets/115128955/8d4d6068-f10a-44a3-a568-72c15dd5d4f0)

### iii) Display the video by resizing the window
![IMG-20240305-WA0006](https://github.com/sanjay5656/Image_Acqusition-_using_Web_Camera/assets/115128955/207ed12e-af4f-4538-854c-3946e98ece40)

### iv) Rotate and display the video
![IMG-20240305-WA0008](https://github.com/sanjay5656/Image_Acqusition-_using_Web_Camera/assets/115128955/373b964f-30c5-440c-8904-fc6a4557e553)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
