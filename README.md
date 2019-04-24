# Automatic-Hole-Filling
Automatic Hole Filling on Binary Image using Geodesic Dilation
Step 1: Form a marker image F with
        F(x,y) = 1 - I(x,y) if (x,y) is on the border of the image.
               = 0 otherwise
Step 2: Form a mask as G = complement of (I(x,y))
Step 3: Peform the morphological reconstruction using geodesic dilation with G as the mask and F as the marker image to get R
Step 4: Obtain the complement of R as the output

Original Image
![alt text](https://github.com/hqdang/Automatic-Hole-Filling/blob/master/fingerprint.jpg)

Binary Image
![alt text](https://github.com/hqdang/Automatic-Hole-Filling/blob/master/fingerprint_bw.png)

Mask obtain with SE = [3,3]
![alt text](https://github.com/hqdang/Automatic-Hole-Filling/blob/master/mask_boundary_3.png)

Mask obtain with SE = [7,7]
![alt text](https://github.com/hqdang/Automatic-Hole-Filling/blob/master/mask_boundary_7.png)

Output image with 300 iterations of morphological reconstruction
![alt text](https://github.com/hqdang/Automatic-Hole-Filling/blob/master/fingerprint300.png)

Output image with 1000 iterations of morphological reconstruction
![alt text](https://github.com/hqdang/Automatic-Hole-Filling/blob/master/fingerprint1000.png)

# Results
We can see the difference between the mask using SE kernel [3,3] and [7,7]. For the kernel [7,7] the hole inside each objects within the picture is filled with 0. This means that the algorithm can fill the inside of these objects much better than using SE kernel [3,3]. Therefore we chose to go with SE kernel [7,7]
The output image is a slight improvement of the binary image version. It's hard to see the difference unless they are overlayed on top of one another. There's  no difference between going through 300 iterations and 1000 iterations. 
