# Interpretable-Neural-Net
Inspiration for a 1 layer interpretable neural net with a single linear form layer for signal extraction

## Some results

Here are two neural networks run on CIFAR10 with the VGG neural network (a traditional neural network found in the literature).

One uses the single interpretable linear "summary" layer, and the other uses the standard "base" VGG non-linear sequence of layers.

![vgg comparison](https://raw.githubusercontent.com/AskExplain/Interpretable-Neural-Net/main/vgg.png)


## Some explanations

The model below explains more about the idea - for a single linear form layer

Where Y are the label responses to be predicted while X is the observed data (e.g. convolutions applied to images)

However, given it is a neural network layer, the "layer model" only learns a decomposition of X - in such a way that it fits the following properties:


![the single layer model](https://raw.githubusercontent.com/AskExplain/Interpretable-Neural-Net/main/main_model.png)


Essentially, linear forms find a latent component Z, followed by a learnable filter set b

Here, X b is equivalent to the latent component multiplied by the covariance of the filters b_transpose b



## An extra property

Based on orthgonality, it is possible to reduce the total computations of the summary layer proposed above. Rather than computing an inverse operation every time the summary layer is called - neural networks can take advantage of the simple matrix mulitplication that leads to an equivalent expression ...

![the single layer properties](https://raw.githubusercontent.com/AskExplain/Interpretable-Neural-Net/main/properties.png)

Notice that the latent components Z is now equivalent to X b which is equivalent to X b (b_transpose b).

The loss function given X, which here are the convoluted features along with the linear weights b can now be expressed along with the labels Y in the loss function:

![the single layer loss function](https://raw.githubusercontent.com/AskExplain/Interpretable-Neural-Net/main/loss_function.png)



## One more property on linearity and non-linearity

There is a well and definite link between the linear expression of this model with the non-linear expression of deep neural networks. 

To see how, propose the following:


![the linear and nonlinear relations](https://raw.githubusercontent.com/AskExplain/Interpretable-Neural-Net/main/nonlinear_property.png)



Hello  World  
