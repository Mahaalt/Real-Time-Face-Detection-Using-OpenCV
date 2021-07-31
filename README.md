# Real-Time Face Detection Using OpenCV


This task is done using Python, it is a Real-Time Face recognition using OpenCV while performing object detection using Haar feature-based cascade classifiers for detecting a face.

---

## Import

Start by importing OpenCV 

    import cv2

---

## Initialize and load the cascade

Initialize a variable that contain the Face Haar Cascade and use its path to load it into your project.

    face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')

---

## Capture the webcam or video file

To capture video from webcam: 

    cap = cv2.VideoCapture(0)

To use a video file as input:

     cap = cv2.VideoCapture('filename.mp4')
     
---

## Call the classifier function

We will make a loop and set the camera or video on it.

    while True:
          # Read the frame
          _, img = cap.read()

          # Convert to grayscale
          gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

---

## Detect the faces

The function will detect faces on the image using a blue rectangle on each face:

         # Detect the faces
         faces = face_cascade.detectMultiScale(gray, 1.1, 4)

         # Draw the rectangle around each face
         for (x, y, w, h) in faces:
         cv2.rectangle(img, (x, y), (x+w, y+h), (255, 0, 0), 2)

---

## Final things

When the user press on Esc button, he will exit from the program.

    # Stop if escape key is pressed
    k = cv2.waitKey(30)
    if k==27:
        break

    # Display
    cv2.imshow('img', img)
 
    # Release the VideoCapture object
    cap.release()

---

## Output


https://user-images.githubusercontent.com/71232960/127731440-f734cc1c-32aa-4ea0-b81f-223e42566153.mp4


