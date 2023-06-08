# ThePoolGenius
Goal: Detect the best hit on a pool game, when the image taken from different points of view. The program returns the ball and hole for the best hit. <br>
Environment: Jupyter Notebook, Python, OpenCV. <br>
Note that the program supports images of green pool tables, taken from a point of view which all the table (including all pockets) is visible to the camera.


# Steps

1. Find green objects in the image using a mask:
<img src="https://github.com/orcohents/ThePoolGenius/assets/109345354/e560fbd5-e70f-41ee-91d7-0036fcc78087 " width="250" height="250">

2. Find four lines which form the border of the pool table:
<img src="https://github.com/orcohents/ThePoolGenius/assets/109345354/f4b984a8-3346-44e8-9538-bb9e00146357" width="250" height="250">

3. Find the intersection points between the lines:
<img src="https://github.com/orcohents/ThePoolGenius/assets/109345354/4a113c63-ec07-4371-aedc-72bbfe8593ce" width="250" height="250">

4. Apply perspective transformation on the image using the four points:
<p float="left">
  <img src="https://github.com/orcohents/ThePoolGenius/assets/109345354/1754805b-bb7f-4f73-b7b9-db53dbad1445" width="150" />
  <img src="https://github.com/orcohents/ThePoolGenius/assets/109345354/73d2914c-e628-498f-8afd-c55d0fddd746" width="150" /> 
</p>

5. Balls detection: 
 * finding contours of objects on the table:
 <img src="https://github.com/orcohents/ThePoolGenius/assets/109345354/8a761f26-7551-4d69-a460-a46c6861d5a9" width="150">
 
 * filtering unwanted contours by size, color and location in the image:
 <img src="https://github.com/orcohents/ThePoolGenius/assets/109345354/3f4edf35-72e9-4e67-a15b-c1d0af6db508" width="150">


6. Color detection: calculate the mean pixel value of each ball, which gives us the ball's color:
<img src="https://github.com/orcohents/ThePoolGenius/assets/109345354/5c178c75-4bb5-423e-9531-43c030207730" width="150">

7. Generate a table drawing to get a better point of view, using the balls locations and colors we found:
<img src="https://github.com/orcohents/ThePoolGenius/assets/109345354/eb864e74-a8c4-47c2-b2de-3942ebd1e8f9" width="150">

8. Iterate through every pair of (ball,hole) to find the ball and hole that are following the conditions for the best hit:
<img src="https://github.com/orcohents/ThePoolGenius/assets/109345354/1c73e027-6b26-4d71-868c-ad73b3ae1b58" height="150" >

