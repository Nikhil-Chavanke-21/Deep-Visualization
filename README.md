# Deep Visualization for Convolutional Neural Networks
#### This is a code for visualizing how convolutional neural networks function while performing the Classification/Detection Tasks.


The code has a class visualize. You can initialize the class using any pretrained networks which are available in pytorch.

     model=models.alexnet(pretrained=True)
     device=torch.device("cuda" if torch.cuda.is_available() else "cpu")     
     v=visualize(model, device)
Here I am using alexnet, any other network like suppose vgg16 can be passed.

#### Code has 2 callable methods:
### Method 1:visualize:
Basically this method implements Deconvolution technique in the paper [Zeiler and Fergus(DeconvNet)](https://arxiv.org/abs/1311.2901). For more details you can read the paper.

The visualize method takes as input a image, to pass to the network and the convolution layer(number) for which the filters are to be visualized. Like alexnet has 5 conv. layers, you can enter 1-5.
     
     image=cv2.imread("drive/My Drive/data/face.jpeg" )
     image=image[:,:,[2,1,0]]
     v.visualize(image, 3)
When you run the code in colab the output of visualize shows 2 things. First it shows the activations in all the channels(i.e. feature maps) in the layer given as input. Next it gets all the channels which have maximum activation magnitude and shows what parts of image are responsible for activating those channels. Like 88th filter is responsible for detecting the eyes. And in the activations also, if you see there are 2 white spots in the feature map.

### Method 2:construct:
The construct method takes as input a conv. layer number and the filter number in that layer.

     v.construct(3, 88)
This method construct a image/patterns, such that the image that maximizes activations in that filter of the layer. First random image is initialized. And then the values of the pixels are regressed to produce maximum activation of the feature map corresponding to a filter using backtracking.

Lets see an example:

We pass this image to visualize.

![](https://github.com/Nikhil-Chavanke-21/Deep-Visualization/blob/master/data/face.jpeg)

This are the activation for filter 88 of conv. layer 3 alexnet. We can see that this filter detects the eye.

![](https://github.com/Nikhil-Chavanke-21/Deep-Visualization/blob/master/data/pattern)

This is the deconvolutionalized image from that activation.

![](https://github.com/Nikhil-Chavanke-21/Deep-Visualization/blob/master/data/deconv)

Here we can see eye like patterns, so such patterns produce high activations for that filter.

![](https://github.com/Nikhil-Chavanke-21/Deep-Visualization/blob/master/data/activation)

## References
[Zeiler and Fergus(DeconvNet)](https://arxiv.org/abs/1311.2901)
