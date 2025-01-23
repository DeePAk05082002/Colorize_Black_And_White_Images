# Colorize Black and White Images

This project demonstrates the use of deep learning to colorize black-and-white images using a pre-trained neural network model.

## Overview
The project leverages the following technologies:
- OpenCV's Deep Neural Network (DNN) module for model loading and inference.
- A pre-trained model for image colorization developed by Richard Zhang et al.

## Features
- Converts black-and-white images to vibrant color images.
- Utilizes a Caffe-based deep learning model.
- Provides a user-friendly command-line interface for inputting image paths.

## Prerequisites
Before running the project, ensure you have the following installed:
- Python 3.6 or later
- OpenCV (cv2) library
- NumPy

## Model Files
Download the required model files from the following sources:
1. **colorization_deploy_v2.prototxt**:    [GitHub Link](https://github.com/richzhang/colorization/tree/caffe/colorization/models)
2. **pts_in_hull.npy**: [GitHub Link](https://github.com/richzhang/colorization/blob/caffe/colorization/resources/pts_in_hull.npy)
3. **colorization_release_v2.caffemodel**: [Drive Link](https://drive.google.com/file/d/1AilvQt8UBWzW6TMN5CdO0Ycg9I5g50HN/view?usp=drive_link)

## Usage
1. Clone the repository or download the code.
2. Set the `DIR` variable in the script to the folder containing the downloaded model files.
3. Run the script using the following command:
   ```bash
   python colorize.py --image path/to/your/black_and_white_image.jpg
   ```

## Code Explanation
### Main Steps:
1. **Load the Pre-Trained Model**:
   - Load the `.prototxt` file and `.caffemodel` file using OpenCV's DNN module.
   - Load the `pts_in_hull.npy` file for ab channel quantization.

2. **Prepare the Input Image**:
   - Convert the image to the LAB color space.
   - Resize the image to the required input size for the model (224x224).
   - Extract the L channel and normalize it.

3. **Perform Colorization**:
   - Pass the processed L channel through the model.
   - Generate the ab channels and resize them back to the original image dimensions.
   - Merge the L and ab channels to form a colorized image in the LAB color space.
   - Convert the LAB image back to the BGR color space.

4. **Display the Results**:
   - Show both the original and colorized images using OpenCV.

## Example
### Input
A grayscale image of a landscape.
![nature](https://github.com/user-attachments/assets/43c7f9bf-0a59-4ee4-88d1-e0e95be9618f)


### Output
A colorized version of the input image.
![image](https://github.com/user-attachments/assets/3916967c-9966-471f-891d-f5d8234bd110)


## Credits
This project is based on the following resources:
1. [OpenCV DNN Sample](https://github.com/opencv/opencv/blob/master/samples/dnn/colorization.py)
2. [Richard Zhang's Colorization Work](http://richzhang.github.io/colorization/)
3. [GitHub Repository](https://github.com/richzhang/colorization/)

## License
This project is for educational purposes only. Refer to the original resources for licensing details.

