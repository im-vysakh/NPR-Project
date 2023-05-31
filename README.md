# ANPR-Project

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

##  SOFTWARE MODEL
The main and the most important portion of this system is the software model. The software model use series of image processing techniques which are implemented in OPEN CV. The ANPR algorithm is broadly divided into three parts:

• Capture image

• Extract the plate from the image

• Recognize the numbers from the extracted plate

The first step is the capturing of an image using the USB camera connected to the PC. The images are captured in RGB format so it can be further process for the number plate extraction. The second step of the ANPR algorithm is the extraction of the number plate in an image. A yellow search algorithm is used to extract the likelihood ROI in an image. As the official number plate of Sindh has yellow background with alphanumeric character written in
black, it is easy to detect the plate area by searching for yellow pixels. The image is search for the yellow color pixels or some which are closer to yellow in value. If pixel value is of yellow color the pixel is set to 1, otherwise the pixel value is set to 0. The image obtained after the search algorithm is in black and white format. After identify the ROI, image is then filtered using two different filtering techniques. The first technique involves removing of all white patches that are connected to any border and set their pixel value to 0. The second filtering technique use pixel count method to remove the small regions in an image other than the plate region. The number of consecutive white pixels is inspected and regions that contain number of white pixels less than the predefined threshold are set to 0. At this stage the image contains only the vehicle number plate. Smearing algorithm [x] is used next to extract the number plate in an image. The smearing algorithm is search for the first and last white pixels starting from top left corner of an image. The image is then cropped that only contain the vehicle number plate.

The third step of the developed ANRP algorithm uses Optical Character Recognition (OCR) algorithm to recognize the vehicle number. The resultant cropped image obtained after the second step is inverted i.e. all white pixels are converted to black and black pixels to white. Now the text is in white and the plate background is black. Before applying the OCR the individual lines in the text are separated using line separation process. The line separation adds
the each pixels value in a row. If the resultant sum of row is zero that means no text pixel is present in a row and if the resultant sum of row is greater than zero that means the text is present in row. The first resultant sum greater than zero represents the start of the line and after this the first resultant sum equal to zero represents the end of the line. The start and end values of the line is used to crop the first line in the text. The same process continues to separate the second line in the text.

Once the lines in an extracted vehicle number plate are separated, the line separation process is now applied column wise so that individual character can be separated. The separated individual characters are then stored in separate variables. The OCR is now used to compare the each individual character against the complete alphanumeric database. The OCR actually uses correlation method to match individual character and finally the number is identified and stored in string format in a variable. The string is then compared with the stored database for the vehicle authorization. The resultant signals are given according to the result of comparison.

## RESULT
Different images of cars having different colors and structure types are taken and stored in PC. The different effects of the day lights are also considered during the processing. After capturing the image the next step was the yellow search algorithm. Figure 4 shows the images after the executing the yellow search algorithm. The white region represents the yellow or color closer to the yellow. It can be observed that the yellow search algorithm successfully detect the ROI that only contain vehicle number plate. The smearing algorithm used next to extract the vehicle number plate as shown in figure 5. Once the vehicle number plate is extracted, it is converted into the binary format. Figure 6 and figure 7 show the binary and inverted binary format respectively. The row and column segmentations methods are used next to extract the individual character in the vehicle number plate. The results of the row and column segmentation are shown in figure 8 and figure 9 respectively. Finally OCR is used for character recognition and each and every alphanumeric character is recognized 

![p1](https://github.com/im-vysakh/NPR-Project/assets/134374340/8d223bcf-4b30-47f1-a40b-6ca1a852f7a8) 
![p2](https://github.com/im-vysakh/NPR-Project/assets/134374340/aee8c58c-b6a5-4412-8163-3622a1fbbf78)
![p3](https://github.com/im-vysakh/NPR-Project/assets/134374340/1ea0b3a0-79b5-481e-9e41-9cbf6753dc68)
![p4](https://github.com/im-vysakh/NPR-Project/assets/134374340/3d55e6ef-03df-4e36-9f0e-0fc40bc7d0b1)
![p5](https://github.com/im-vysakh/NPR-Project/assets/134374340/3533e07f-5e3b-45c6-bf0c-f705706c5baf)
![p6](https://github.com/im-vysakh/NPR-Project/assets/134374340/507c4f84-0de8-4628-b5d9-f7134ee8a126)
