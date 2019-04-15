# Airbus Ship Detection

These notebooks detail my solution to Kaggle's [Airbus Ship Detection](https://www.kaggle.com/c/airbus-ship-detection) challenge. This solution scored 139 out of 884 for the competition.

The goal of the competition is to analyze satellite images of container ships and produce segmentation masks of the ships, like so:

<img src="https://github.com/kheyer/Airbus-Ship-Detection/blob/master/00ce2c1c0.jpg" width="50%" height="50%">

<img src="https://github.com/kheyer/Airbus-Ship-Detection/blob/master/00ce2c1c0_mask.png" width="50%" height="50%">

To generate solutions, I created a two model pipeline. The first model is a ResNeXt50 based classification model that classified images as containing ships or not containing ships. The second model is a ResNet34 based U-Net model that generated segmentation masks for images classified as ships. The two model solution worked much better than training a U-net segmentation model to process all images.

The solution is broken up into several notebooks:

#### Notebook 0: Challenge Overview and Approach
This notebook discusses the competition and some challenges related to the dataset

#### Notebook 1: Preparing Masks as Images
Ground truth segmentation masks are provided as run length encoded strings. This notebook turns encoded masks into images.

#### Notebook 2: Training the Segmentation Model
This notebook shows training the segmentation model and some of the tricks used to maximize performance

#### Notebook 3: Training the Classification Model
This notebook shows training the classification model

#### Notebook 4: Generating a Submission
This notebook shows using the two-model approach to filter ship containing images with the classification model, then generating segmentation masks for ship containing images using the segmentation model. Predicted masks are converted into run length encoded strings for the solution.
