# Check the answer sheet

This application is for android devices and uses the OpenCV library for detection!

## Answer sheet
In this project, I use the Aruco library for the detection of markers. I create it for demonstration so it has 10 questions, in the future I will create more templates! I designed the answer sheet with Aruco markers like this: 

![Answer Sheet](/image_readme/Answer_Sheet.png)  

As you see, the Answer sheet has two parts:
- Maker: It has a marker that is used to detect the answer sheet. They have Id from 0 to 3.
- Answer: It is designed with columns and rows with space between them. They have evenly spaced so that you can easily detect the answer by the position of the marker.

## Processing in the detect answer sheet

This is the result of step by step process of detecting the answer sheet.  

![Algorithm](/image_readme/Algorithm.png)  

- **Step 1:** Convert the image to grayscale. Because the detection is based on a grayscale image and the answer sheet is black and white, it is easier to detect and run faster without working on 3 channels color image.  
- **Step 2:** Using the Aruco library, detect the marker. The answer sheet has 4 markers, so if the Aruco library detects 4 markers, it will return 4 corners of the marker. After that, I will wrap the sheet with the corners of the marker.  
- **Step 3:** Convert grayscale image to binary image. I use the threshold function to convert grayscale images to binary images. Convert to binary image help procession easier, because we just care about true or false. Besides, it helps detection more exactly.  
- **Step 4:** After detection for each answer, I mark the correct answer with the green circle, the wrong answer with the red circle, and if the wrong answer, it will show the correct answer with the blue circle.  
- **Step 5:** After having the result, I convert each answer to the original position. This step help user can see the result more clearly.  