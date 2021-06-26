# Multi-label, Multi-class Classification of Image Data
**COMP 551: Applied Machine Learning** <br />
**Authors: Viet Hoang, Aaron Nadal, Diallo Oballa**

Image recognition has become a major field of research due to its wide range of applications from lesion detection in medical imaging to facial recognition in photography. Convolutional neural networks (CNNs) are one of the most commonly used techniques in computer vision. The main problem with CNNs that initially arose is that deeper networks started to perform worse [1]. 

In 2015, a Microsoft research team (He et al.) pro-posed a new architecture involving residual learning (Fig 1) that allowed the CNN to more easily learn the desired underlying function `H(x)`. `H(x)` can be defined as `H(x) := F(x) + x` where `F(x)` is the residual. The new architecture, named ResNet, learns `F(x)` instead of `H(x)`. This allows the model to more easily learn the indentity mapping by just setting `F(x)` to 0, giving `H(x) = x` [1]. 

![mnist_example](https://user-images.githubusercontent.com/44730503/123496936-c0e87e80-d5f8-11eb-98cc-ef1e9fbc1afb.png)
<p align="center"> Figure 1: Sample data from MNIST dataset  </p>

This architecture served as the foundation of the model used in this project to classify digits from a modified MNIST dataset. By using a residual framework, we were able to a create deeper neural network without losing accuracy. We implemented an 18-layer residual neural network (ResNet-18). He et al. built deeper networks (ResNet-34, ResNet-50, ResNet-101 and ResNet-152), but we decided against using those models due to their training times.

We found that our model classified the data veryaccurately, producing 99.619% accuracy on 60% ofthe test data on Kaggle.

## Datasets and Data Augmentation
We used a modified MNIST data set containing one-to-five digits ranging from 0 to 9. The number 10 is used to label images with less than five written digits. In an effort to improve our model, we implemented data augmentation. The size of the dataset was increased by applying a transformation to the training images and appending it to our training dataset. Many different transformations were considered, but in the end only a shear of randomly chosen magnitude between −25◦ and 25◦ was applied.

## Results
We trained multiple models with varying number of epochs, ResNet architectures and batch sizes. Our highest performing model was achieved with the modified ResNet18 architecture over 200 epochs and with a batch size of 16 which resulted in an accuracy of 99.619% on the testing data.

## References
1. Kaiming He et al. “Deep Residual Learning for Image Recog-nition”. In:CoRRabs/1512.03385 (2015). arXiv: 1512.03385. URL: http://arxiv.org/abs/1512.03385.
