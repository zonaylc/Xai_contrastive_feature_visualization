# Xai_contrastive_feature_visualization(Explainable AI Assignment 2 - Model Explanations)
A visualization approach to explain how a deep learning model classify the hand-written digits.

### Model & Data

#### Dataset
Our group will use MNIST Datasets. The dataset consist of pictures of hand-drawn numbers with 28x28 pixels, in grayscale. Each pichture is classified by a number from 0 to 9. Alltogether the dataset has 60.000 individual datapoints for training as well as an additional 10.000 datapoints for testing.

If we have time and we may also apply our approches to other similar datasets like the Fashion-MNIST set, which also consists of 60.000 + 10.000 28x28 pixel pictures in grayscale but instead of numbers they classify zalando articles in ten categories.

We are trying to explain a convolutional neural network. For the Grand tour approach the network is a simple classifier network with 3 convolutional layers and a dense classifier. For the second approach additionaly to this network structure before the last layer of the classifier the network is split into a classifier in addition to a sample and decoder built in the exact opposite shape as the encoder to create a variational auto-encoder.

The basic structure of the network was chosen by looking through proposed classification networks for MNIST (google) and rebuilt in pytorch.

### Explainability Approache - Contrastive Feature Visualization
https://www.semanticscholar.org/paper/Contrastive-Attribution-with-Feature-Visualization-Quint-Wirka/14647b6fcc52f68fffc593070be7068fd3f57d7f

For this approach, we trained a CNN classifier for a Variational Autoencoder and walk along the latent space (mean and variance) between two different classes instances. Then show the differences by generating an image and classifying the latent space at each step along the way to see when the classification changes.

* Why: Interpretability and Explainability, Education
* Who: Model Users, Non-experts
* What: Aggregated Information
* How: Instance-based Analysis & Exploration, Algorithms for Attribution & Feature Visualization
* When: After Training
* Where: Quint, E., Wirka, G., Scott, S., Vinodchandran, N.V., & Yao, T. (2020). Contrastive Attribution with Feature Visualization.

The result shows Interpret why an instance is classified to  class y, and what differentiates between two classes. We pick up some easy misclassified pairs as examples and visualize what important features the classifier uses to decided which class to classify.  
