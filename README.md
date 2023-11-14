# Automatic Number Plate Recognition using OpenCV

## INTRODUCTION
The Automatic Number Plate Recognition (ANPR) is simply the ability to automatically
extra and recognition a vehicle number plate’s characters from an image. In essence it consists of
a camera or frame grabber that has the capability to grab an image, find the location of the
number in the image and then extract the characters for character recognition tool to translate the
pixels into numerically readable character. ANPR can be used in many areas from speed
enforcement and tool collection to management of parking lots, etc. It can also be used to detect
and prevent a wide range of criminal activities and for security control of a highly restricted
areas like military zones or area around top government offices. The system is computationally
inexpensive compare to the other ANPR systems.

Besides the robustness, the earlier methods use either feature based approached using
edge detection or Hough transform which are computationally expensive or use artificial neural
network which requires large training data. The presented ANPR system is aimed to be light
weighted so that it can be run real time and recognizes Sindh standard number plate under
normal conditions. The ANPR system works in three steps, the first step is the detection and
capturing a vehicle image, the second steps is the detection and extraction of number plate in an
image. The third section use image segmentation technique to get individual character and
optical character recognition (OCR) to recognize the individual character with the help of
database stored for each and every alphanumeric character.

##  TOOLS Used
### 1 CSV FILE
CSV stands for Comma Separated Values. A comma -separated values file is a delimited text file that uses a comma to separate values. Each line of the file is a data record. Each record consists of one or more fields, separated by commas. The use of the comma as a field separator is the source of the name for this file format.

### 2 MODULES USED
1. NumPy: NumPy is a library for the Python programming language, adding support for large, multi-dimensional arrays and matrices, along with a large
collection of high-level mathematical functions to operate on these arrays. Used here for: Converting image to matrix.

2. Open CV: OpenCV stands for Open Source Computer Vision. It is an open source computer vision and machine learning software library. The library
has more than 2500 optimized algorithms, which includes a comprehensive set of both classic and state-of-the-art computer vision and machine learning
algorithms. These algorithms can be used to detect and recognize faces, identify objects, classify human actions in videos, track camera movements, track moving objects, extract 3D models of objects, produce 3D point clouds from stereo cameras, stitch images together to produce a high resolution image of an entire scene, find similar images from an image database, remove red eyes from images taken using flash, follow eye movements,

3. Imutils: Imutils include a series of convenience functions to make basic image processing functions such as translation, rotation, resizing,
skeletonization, and displaying Matplotlib images easier with OpenCV and both Python 2.7 and Python 3. Used here for: Resizing the image.

4. Pytesseract: Library to use the Tesseract-OCR. Tesseract is an optical character recognition engine for various operating systems. Tesseract is
considered to be one of the most accurate open-source OCR engines available. What is OCR? Optical character recognition or optical character reader is the electronic or mechanical conversion of images of typed, handwritten or printed text into machine-encoded text, whether from a scanned document, a photo of a document, a scene-photo or from subtitle text superimposed on an image. Used here for: Converting cropped number plate image obtained into text.

5. Pandas: In computer programming, pandas is a software library written for the Python programming language for data manipulation and analysis. Used here for: Converting data extracted to a Data Frame.

6. Time: The time() function returns the number of seconds passed since epoch.

## PROCEDURE
1. Read the original image

2. Resize the image

3. Convert it to grayscale.

4. Apply Bilateral Filter (bilateral filter is a non-linear, edge-preserving, and noise-reducing smoothing filter for images. It replaces the intensity of each pixel with a weighted average of intensity values from nearby pixels)

5. Identify and store the Canny edges (the Canny edge detector is an edge detection operator that uses a multi-stage algorithm to detect a wide range of edges in images)

6. Find the contours in from the edges detected and sort the top 30 contours.

7. Get the perimeter of each contour and select those with 4 corners.

8. Mask all other parts of the image and show the final image.

9. Read the text using Tesseract OCR.

10. Append to CSV file.

## RESULT

![p1](https://github.com/im-vysakh/NPR-Project/assets/134374340/8d223bcf-4b30-47f1-a40b-6ca1a852f7a8) 
![p2](https://github.com/im-vysakh/NPR-Project/assets/134374340/aee8c58c-b6a5-4412-8163-3622a1fbbf78)
![p3](https://github.com/im-vysakh/NPR-Project/assets/134374340/1ea0b3a0-79b5-481e-9e41-9cbf6753dc68)
![p4](https://github.com/im-vysakh/NPR-Project/assets/134374340/3d55e6ef-03df-4e36-9f0e-0fc40bc7d0b1)
![p5](https://github.com/im-vysakh/NPR-Project/assets/134374340/3533e07f-5e3b-45c6-bf0c-f705706c5baf)
![p6](https://github.com/im-vysakh/NPR-Project/assets/134374340/507c4f84-0de8-4628-b5d9-f7134ee8a126)
