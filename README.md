# Image_Acqusition-_using_Web_Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
<br>
Use cv2.Videocapture(0) at access web camera

### Step 2:
<br>
Use cv2.imread to read the video or image

### Step 3:
<br>
Use cv2.imwrite to save the image

### Step 4:
<br>
Use cv2.imshow to show the video

### Step 5:
<br>
End the program and close the oupput video window by pressing 'q'

## Program:
``` Python
### Developed By: YESHWANTH P
### Register No: 212222230178

## i) Write the frame as JPG file
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("yeshwanth.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()

## ii) Display the video
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Hibiscus',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230178-Yeshwanth P',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230178-Yeshwanth P',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![Screenshot 2024-03-22 123445](https://github.com/Yeshwanthperumal/Image_Acqusition-_using_Web_Camera/assets/119476088/56716d90-2b19-4dae-aec9-900b38a38652)

### ii) Display the video
![image](https://github.com/Yeshwanthperumal/Image_Acqusition-_using_Web_Camera/assets/119476088/d6c8beb1-9824-4475-8a35-f1d67e82e764)

### iii) Display the video by resizing the window
![image](https://github.com/Yeshwanthperumal/Image_Acqusition-_using_Web_Camera/assets/119476088/62f53256-2daa-452d-a30f-419224ea97e6)

### iv) Rotate and display the video
![image](https://github.com/Yeshwanthperumal/Image_Acqusition-_using_Web_Camera/assets/119476088/5a1f464d-471f-49bf-8558-e6fe2b710bb7)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
