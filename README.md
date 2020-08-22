# Deep-Visualization
This is a code for vizualizing how convolutional neural networks funtion and perform the Classification and Detection Tasks.

Basically there is a class visualize.

You can initialize the class using any pretrained networks which are available in pytorch.

Ex:  model=models.alexnet(pretrained=True)
     device=torch.device("cuda" if torch.cuda.is_available() else "cpu")
     v=visualize(model, device)
Here we are using alexnet, you can use any other network as vgg16.
There are 2 methods callable methods:
Method 1:


Tool for vizualizing the filter activations for all layers in the convolutional neural network and understanding the networks using Deconvolution Technique
