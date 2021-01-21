# linearBCV-modified
Modifications to the deedsBCV program written by Dr. Mattias Heinrich for the Nia Lab Group at BU. 

To modify the program I focused the linearBCV.cpp file of the program. The purpose of my modifications was to save the output of the affine transform 
(pre-deformation) to a compressed Nifti file that could be manipulated/imported in MATLAB. 

The summary of the changes is as follows below: 
- Pre-allocate output variables to save the transform object to 
- Call writeOutput function (already defined)
- Call warpAffine function (already defined)
- Iterate through the size of the warped object
  --> Ensure the parameters match the pre-affine transformation object 
- Call gzWriteNifti function
  --> Write post-affine transform to a compressed Nifti file 
- Repeat with segmentation variables as a catch block 
  --> Applies & saves transform if segmentation is a moving image

