# Image-Acquisition-from-Web-Cameraa
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
Use VideoCapture(0) to access web camera
### Step 2:
Use imread to read the video or image
### Step 3:
Use imwrite to save the image
### Step 4:
Use imshow to show the video
### Step 5:
End the program and close the output video windows by pressing 'q'.
## Program:

### Developed By:ADHITHYA.S
### Register No:212222240003
``` Python
## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("jeeva.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()




## iii) Display the video by resizing the window

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




## iv) Rotate and display the video



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
![image](https://github.com/s-adhithya/Image-Acquisition-from-Web-Cameraa/assets/113497423/c8f28289-0663-46fc-9802-860678da8ab7)

### ii) Display the video
![image](https://github.com/s-adhithya/Image-Acquisition-from-Web-Cameraa/assets/113497423/11c41e8d-b674-44dc-b465-71181a6fae7f)


### iii) Display the video by resizing the window
![image](https://github.com/s-adhithya/Image-Acquisition-from-Web-Cameraa/assets/113497423/d4d1ef2c-2e7d-487b-b745-f61cef4f472e)


### iv) Rotate and display the video
![image](https://github.com/s-adhithya/Image-Acquisition-from-Web-Cameraa/assets/113497423/f4d6e73b-19a1-4872-86bf-5e630e1c39bc)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
