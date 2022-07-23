Most existing approaches to visual odometry are based on the following stages.      

Acquire input images: using either single cameras. stereo cameras,or omnidirectional cameras.     
Image correction: apply image processing techniques for lens distortion removal, etc.     
Feature detection: define interest operators, and match features across frames and construct optical flow field.    
Feature extraction and correlation.   
Use correlation, not long term feature tracking, to establish correspondence of two images.   
Construct optical flow field (Lucas–Kanade method).   
Check flow field vectors for potential tracking errors and remove outliers.   
Estimation of the camera motion from the optical flow.      
Choice 1: Kalman filter for state estimate distribution maintenance.    
Choice 2: find the geometric and 3D properties of the features that minimize a cost function based on the re-projection error between two adjacent images. This can be done by mathematical minimization or random sampling.      
Periodic repopulation of trackpoints to maintain coverage across the image.     
