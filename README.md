#                                                Pose Estimation 
## Abstract


Pose estimation is the localization of human joints in images or videos. 
The goal is to estimate a 2D pose (x,y) coordinates for each joint from a RGB image
Vision based human pose estimation is an non-invasive technology for human-computer interaction (HCI). Direct use of the body as an input device provides an attractive interaction method, with minimum need for specialized equipment, such as sensors, but a camera and a processing platform.
In this project, using latest Convolutional Neural Network architectures, we create a module that it could be deployed on an any pc with camera.

## Dataset

For the purpose of the project CMU Panoptic Dataset is used.(http://domedb.perception.cs.cmu.edu/dataset.html)

![Image description](http://domedb.perception.cs.cmu.edu/media/categoryFigures/range_of_motion.jpg)

This dataset provides full body HD images as along with the coordinates of human joints in each image.

Because the project was made in a average computer(GTX 1080) and there was no option training the model on the cloud,due to huge dataset that comes with many training hours, we redifined the size of the image and the groundtruth to be 224x224x3.

Tf records for the images and labels are used to build a solid input pipeline in order to train efficiently our model.


## Training

The first presented architecture is based on idea of ResNets.

The core idea of ResNet is introducing a so-called “identity shortcut connection” that skips one or more layers.
Each layer obtains additional inputs from his previous one.

![Image description](https://user-images.githubusercontent.com/6441756/33684878-9bb8a89c-da84-11e7-8057-fc75c40aa778.png)


The authors refined the residual block and proposed a pre-activation variant of residual block , in which the gradients can flow through the shortcut connections to any other earlier layer unimpededly.


![Image description](https://i.stack.imgur.com/0mE2p.png)


The second architecture is based on the very successful idea of DenseNets. In a DenseNet, each layer obtains additional inputs from all preceding ones and propagates its own feature-maps to all subsequent layers, by a channel-wise concatenation.


![Image description](https://miro.medium.com/max/1560/1*rmHdoPjGUjRek6ozH7altw.png)
 
