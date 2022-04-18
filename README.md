# Interpretable-Neural-Net
Inspiration for a 1 layer interpretable neural net with a single linear mixed form layer for signal extraction


## Some explanations

The model below explains more about the idea - for a single linear mixed form layer, it is essentially the fixed part of the model, that is

Y a = X b

Where Y are the label responses to be predicted while X is the observed data (e.g. convolutions applied to images)

However, given it is a neural network layer, the "layer model" only learns a decomposition of X - in such a way that it fits the following properties:


![the single layer model](https://raw.githubusercontent.com/AskExplain/Interpretable-Neural-Net/main/model.png)


Essentially, linear mixed forms find a latent component Z, followed by a learnable filter set b

Here, X b is equivalent to the latent component multiplied by the covariance of the filters b_transpose b



## An extra property

Based on orthgonality, it is possible to reduce the total computations of the summary layer proposed above. Rather than computing an inverse operation every time the summary layer is called - neural networks can take advantage of the simple matrix mulitplication that leads to an equivalent expression ...

![the single layer model](https://raw.githubusercontent.com/AskExplain/Interpretable-Neural-Net/main/properties.png)

Notice that the latent components Z is now equivalent to X b which is equivalent to X b (b_transpose b).

The loss function given X, which here are the convoluted features along with the linear weights b can now be expressed along with the labels Y in the loss function:

![the single layer loss function](https://raw.githubusercontent.com/AskExplain/Interpretable-Neural-Net/main/loss_function.png)


