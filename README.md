# Semantic Segmentation on KITTI Road Dataset
## Deep Learning for Computer Vision
---

![](Processed_KITTI_dataset.gif)

### The Project
In this project, Fully Convolutional Network (FCN) are used to label the pixels of a road in images/video.

Since we want to maintain spatial dimensions of the image we use FCN instead of deep convolutional network. The latter excels at extracting meaningful features from the input and doesn't maintain the original dimensions.

The FCN up-samples the output from VGG16 using 1x1 Convolutions. We also add skip connections to make up for the information loss from down-sampling of the encoder. This way the network can use information from multiple resolutions.

Overall FCN uses 3 techniques:
1. 1 x 1 Convolutions
2. Transposed Convolutions
3. Skip connections

The results are obvious in the video above

#### Parameters
After tunning the following parameters were used for the best results:
* Epochs : 15
* Batch Size : 8
* Learning Rate : 0.00005

#### Trained on AWS using the g3.4x instance

### Requirements
##### Frameworks and Packages
The following packages are required:
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)
##### Dataset
Download the [Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) from [here](http://www.cvlibs.net/download.php?file=data_road.zip).  Extract the dataset in the `data` folder.  This will create the folder `data_road` with all the training a test images.

### Use
##### Run
Run the following command to run the project:
```
python main.py
```
**Note** If running this in Jupyter Notebook system messages, such as those regarding test status, may appear in the terminal rather than the notebook.

From Self-Driving Car Engineer Nanodegree Program, Starter Code Provided by Udacity
