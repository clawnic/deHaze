# Single-Image-Dehazing-Python
A Python-based approach for efficient image dehazing, utilizing boundary constraints and contextual regularization.

## Installation and Running the Tests

### Cloning the Repository
```
git clone https://github.com/your-username/Single-Image-Dehazing-Python.git
cd Single-Image-Dehazing-Python
```

### Usage
```python
import cv2  # OpenCV for image processing
import numpy as np  # NumPy for numerical operations

HazeImg = cv2.imread('image_path')  # Read input image (**must be a color image**)

# Apply dehazing algorithm
# (Implement your dehazing function here)
HazeCorrectedImg = dehaze_function(HazeImg)  

cv2.imshow('input image', HazeImg)  # Display the original hazy image
cv2.imshow('enhanced_image', HazeCorrectedImg)  # Display the result
cv2.waitKey(0)  # Hold the display window
```

### User-Controllable Parameters (Default Values):
```
airlightEstimation_windowSze=15
boundaryConstraint_windowSze=3
C0=20
C1=300
regularize_lambda=0.1
sigma=0.5
delta=0.85
showHazeTrasmissionMap=True
```

### Running the Code
1. Go to the `src` folder.
2. Run the file `example.py`.
3. Sample images are stored in the `Images/` folder.
4. Output images will be stored in the `outputImages/` folder.

## Required Libraries:
- numpy==1.19.0
- opencv-python
- scipy

## Algorithm Overview:
This method for image dehazing involves the following steps:
- Airlight estimation
- Calculating boundary constraints
- Estimate and refine transmission
- Perform dehazing using the estimated airlight and transmission

## Results
![2](https://user-images.githubusercontent.com/13918778/84451507-1cbbb180-ac08-11ea-816f-8ec983fd370d.JPG)
============================================================================================================
![1](https://user-images.githubusercontent.com/13918778/84451353-b0d94900-ac07-11ea-8f1b-3791e9f2f600.JPG)
============================================================================================================
![3](https://user-images.githubusercontent.com/13918778/84451641-8471fc80-ac08-11ea-8a7d-59f566b1c3bb.JPG)

## Performance Comparison
Comparison of dehazing output with AOD-Net. AOD-Net results are obtained using a pretrained model.
![image](https://github.com/Utkarsh-Deshmukh/Single-Image-Dehazing-Python/assets/13918778/f61f6906-e466-487b-ad8c-b289b2d95b90)

Some cases where AOD-Net performs better:
![image](https://github.com/Utkarsh-Deshmukh/Single-Image-Dehazing-Python/assets/13918778/c04d8157-40d1-4a92-b3fb-e85f1c50326c)

