# Fully Convolutional Neural Networks for Image Segmentation

## Overview

This project  demonstrates how to build a Fully Convolutional Neural Network (FCN) for semantic image segmentation. The model will be trained on a custom dataset, which is a subsample of the CamVid dataset, containing video frames from a moving vehicle.

### Dataset Description

The dataset contains two main folders:

- **Images**: This folder contains video frames.
- **Annotations**: This folder contains pixel-wise label maps. Each label map represents the segmentation mask for the corresponding image. Each label map has a shape of (height, width, 1) where each pixel's value denotes the corresponding pixel's class. There are 12 classes in total, with the following class names:

   - 0: sky
   - 1: building
   - 2: column/pole
   - 3: road
   - 4: sidewalk
   - 5: vegetation
   - 6: traffic light
   - 7: fence
   - 8: vehicle
   - 9: pedestrian
   - 10: cyclist
   - 11: void

### Steps in the Project

1. **Load and Prepare the Dataset**: Before training, the dataset needs to be preprocessed. This includes resizing the images and label maps, normalizing pixel values, and reshaping the label maps.

2. **Define the Model**: The FCN model consists of a VGG-16 network for feature extraction and an FCN-8 network for upsampling and generating predictions.

3. **Compile the Model**: Configure the model for training by specifying the loss function, optimizer, and metrics. The loss function used is `categorical_crossentropy`.

4. **Train the Model**: Train the model on the dataset, which may take around 30 minutes to achieve approximately 85% accuracy on both the training and validation sets.

5. **Evaluate the Model**: Use intersection-over-union (IOU) and the dice score as metrics to evaluate the model's performance on a test set.

6. **Make Predictions**: Generate segmentation masks using the `predict()` method. The model's output has a shape of (height, width, 12), where each pixel value represents the probability of belonging to a specific class.

7. **Compute Metrics**: Calculate IOU and dice scores to measure the model's performance compared to ground truth masks.

8. **Show Predictions and Metrics**: Visualize the predicted segmentation masks alongside ground truth, with metrics overlaid for evaluation.

This project illustrates the process of building and training an FCN for image segmentation and evaluating its performance on real-world data. The steps provided serve as a guideline for implementing and testing your own segmentation models.


## Screenshots

![FCN-8](https://github.com/hellfire95/Semantic-Image-Segmentation/blob/main/fcn8.png?raw=true)

