# AUT-2802_MachineVision_LeNet5toLeNet3
# -- README --
# LeNet-5 vs LeNet-3

## Context:
### This project is part of a group assignment at UiT that asks:
  1. Modify the LeNet-5 architecture such that instead of 3 conv layers and 2 fc layers it should have 2 conv layers and 1 fc layer.
  2. How can we do that and what changes are needed in LeNet-5 to change it to LeNet-3?
  3. Compare the training plots of LeNet-3 with LeNet-5 and the results from testing the two models (using the same optimizer and number of epochs)
  4. Provide Github code links

## Method:
Example/template code provided by the instructors' github ( https://github.com/puneetnorge/Machine-Vision ) was copied, adapted and experimented with to solve the assigment.  
Two datasets, MNIST and CIFAR-10 were used to experiment and compare the difference between LeNet-5 and LeNet-3.
*   MNIST: Handwritten numbers from 0 to 9
*   CIFAR-10: pictures containing 10 classes of objects (cat, frog, car, boat, ...)

## Solution
  1. The example LeNet-5 model consisted of two conv layers (w/ pooling), two fc layers and one output layer. To modify this model to consist of only 3 layers, two of the inner fc layers were removed.  
  To make both datasets fit through both models, MNIST was transformed from 28x28 -> 32x32 to match the resolution of CIFAR-10. The transformation was done with black-pixel-padding.
  2. For the chosen datasets and the LeNet-5 example code we made LeNet-3 from LeNet-5 by removing two fc layers and modifying the last standing fc layer to correctly reciev the in_features.
  3. The two removed fc layers did not seem to impact the performance of LeNet for the MNIST dataset. This is likely because handwritten numbers have low complexity, and are likely allready "solved" be the LeNet-3 layers. LeNet-5 = LeNet-3 for MNIST.  
  For the CIFAR-10 dataset none of the models perform very well. We suspected the LeNet-5 to outperform LeNet-3, but this didn't happen. What happened was the LeNet-5 started overfitting very early in the training, and seemed to underperform compared to LeNet-3
