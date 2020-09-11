# MRNet VGG, MobileNet, ResNet & Inception v3 v4
### Data Preprocessing:
After studying the MRNet dataset, the data was read as each patient is single dataset entry, giving 1130 in the training set. Instead of taking all slices from every view we only took the three slices in the middle. Giving us (1130,256,256,3) training set for every view.

### Baseline approach
started with building the following well-known networks from scratch using Keras Layers:
• Visual Geometry Group (VGG)\n
• Residual neural network (ResNet)\n
• MobileNet\n
• Inception V3,V5\n

Results:\n
Trained the 4 networks on the abnormal class in order to determine which is better\n
VGG 84.6%\n
ResNet34 82%\n
Inception V3 82.16%\n
MobileNet 81.3%\n

### Transfer Learning
Instead of training the models staring from random state, we coud use transfer learning to start with a better set of networks’ weights trained on famous datasets.I took the VGG network and applied the weights that is trained in the ImageNet dataset, then I trained 9 models one for each view of each class then ensembled them using majority votes between classes.\n

Results:\n
ACL acuuracy: 0.6916\n
Abnormal acuuracy: 0.816\n
Meniscus acuuracy: 0.658\n

