# Interpretable-Neural-Net
Inspiration for a 1 layer interpretable neural net with a single linear mixed form layer for signal extraction


## Some properties and explanations

The model below explains more about the idea - for a single linear mixed form layer, it is essentially the fixed part of the model, that is

Y a = X b

Where Y are the label responses to be predicted, and X is the observed data (e.g. images)

However, given it is a neural network layer, the "layer model" only learns a decomposition of X - in such a way that it fits the following properties:


![the single layer model](https://raw.githubusercontent.com/AskExplain/Interpretable-Neural-Net/main/model.png)


Essentially, linear mixed forms find a latent component Z, followed by a learnable filter set b

Here, X b is equivalent to the latent component multiplied by the covariance of the filters b_transpose b

