# Interpretability Analysis

## Linear Probe Classifiers

The primary idea behind Linear Probe Classifiers is to take layer-wise intermediate representations in some model, and train a linear classifier to attempt to decode some property of interest. The primary goal of such probes is to identify the models creation of "computationally useful" representations, for example the collection of pixel values in some image may be a visually useful representation of the content of the image, but not a computationally useful representation of the image. Continuing the prior example we could think of a neural net that attempts to classify some fact regarding the image as a model that takes the "visually useful" pixel values of the image, converts them into "computationally useful" representations, and then uses these represntations to classify the image. From an information theory perspective, we can look at this approach as attempting to estimate mutual information between an intermediate representation in the model and some property,

In this project we use ridge regression classifiers to probe our model at each layer, attempting to identify when the various parameter values are decodable, hoping to gain some insight into at what stage of the model "computationally useful" represntations of the features of the volatility surface emerge.

## Sparse Autoencoders and Feature Decomposition

If we want to reverse engineer a deep neural network, it seems necessary that we must break it down into smaller parts (so-called features) that we can look at in isolation to the rest of the model.

A key challenge when doing this is the emergent property of neural networks is **polysemanticity**, a property where neurons in a network are activated by seemingly unrelated features. The **linearity theory** suggests that models encode information as directions in the activation space, a seemingly intuitive property. If we heuristically decompose the loss function into 2 parts, we can begin to understand why this property emerges:

$$

## Experiment Results and Discussion
