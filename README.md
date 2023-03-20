# Image-Acquisition-from-Web-Camera
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
Import Opencv Package.

### Step 2:
Capture the Video from the WebCamera.

### Step 3:
Write the image to a file.

### Step 4:
Show the image or the live camera.

### Step 5:
End the program.

## Program:
``` Python
### Developed By: DHIVYA SHRI B
### Register No: 212221230009
```
```
## i) Write the frame as JPG file
import cv2
VidCap2 = cv2.VideoCapture(0)
while(True):
    ret,frame = VidCap2.read()
    cv2.imshow('video_image',frame)
    cv2.imwrite("212221230048.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
    result = False
VidCap2.release()
cv2.destroyAllWindows()
```
```
## ii) Display the video
import cv2
VidCap=cv2.VideoCapture(0)
while(True):
    ret,frame=VidCap.read()
    cv2.imshow('video_image',frame)
    if cv2.waitKey(1) == ord('q'):
        break
VidCap.release()
cv2.destroyAllWindows()
```
```
## iii) Display the video by resizing the window
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = smallerFrame
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = smallerFrame
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()
```
```
## iv) Rotate and display the video
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![video_image 20-03-2023 19_35_40](https://user-images.githubusercontent.com/94505585/226369065-c62be9a6-6e39-4837-a287-3d383c288915.png)


### ii) Display the video
![video_image 20-03-2023 19_39_11](https://user-images.githubusercontent.com/94505585/226370036-c969cc40-4bb9-49b0-aa7b-543cd6d33e9e.png)



### iii) Display the video by resizing the window
![video_image 20-03-2023 19_44_48](https://user-images.githubusercontent.com/94505585/226370125-ecf7fc39-892f-4b01-a30a-15e27443f931.png)


### iv) Rotate and display the video
![frame 20-03-2023 19_46_17](https://user-images.githubusercontent.com/94505585/226370222-ca99b22a-536c-44a4-91ec-ef2a181fb925.png)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
