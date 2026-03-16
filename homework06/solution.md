# Forward Warping 
![image](/homework06/imgs/forward_warping.png)

# Inverse Warping
## line changed 
Below the commented line is what the original code was, the uncommented line is what is was changed too. 
```python3
#destPX = H_mat @ sourcePX
destPX = np.linalg.inv(H_mat) @ sourcePX

#I_transformed[y_dest, x_dest, :] = I[y_source, x_source, :]
I_transformed[y_source, x_source, :] = I[y_dest, x_dest, :]
```
## (how many points do we need to obtain the Hmatrix?).
To compute the Hmatrix you need at 4 points, the 4 corner points of what you are trying to warp. Here order matters I found the order that gives you the correct solution is top left, top right, bottom right, and then bottom left. Any other combination of points gives you malformed images after warping. Below are two examples 

## Top left, Bottom left, Top right, and then bottom right 
![image](/homework06/imgs/non-solution1.png)

## Top left, Bottom Left, Bottom Right, Top right 
![image](/homework06/imgs/non-solution.png)

## Here is the Correct solution (Top left, Top right, Bottom right, Bottom left)
![image](/homework06/imgs/Solution.png)

# Reflections 
- Playing around with `warpingInteractive.py` allowed me to see that order of the points matters when applying warping. As shown above having the incorrect order of points results in images that are rotated or are filled with the color black. This has to do how the points are used to compute the Hmatrix which is used to tranform the original 4 points and the area within to the destination output 4 points. Thus ordering the 4 points in the Hmatrix correctly, results in an image of which we expect. This is because the 4 points in our dst matrix are top left, top right, bottom right, bottom left and out hmatrix computes the transformation needed to tranform a our 1st point to the top left point and so on. Therefore, the ordering of the points when selecting them in the image are important. 
- Doing this homework as well made me understand more deeply the difference between forward warping and inverse warping, and why inverse warping is used when doing warping on images. The main reason is that foward warping produces holes in the resulting image because you are taking points in the src img and mapping them directly into the dst img. This results in holes/gaps which are not filled in and gives us an incomplete picture. Whereas, inverse warping takes a dst point and find the resulting src point, perform interpolation on src point and then copy it to the dst point. This results in an image that is completely filled in and is something we expect. 