# Deep Visualization for Convolutional Neural Networks
#### This is a code for visualizing how convolutional neural networks function and perform the Classification and Detection Tasks. Multiple methods will be used for this. One is deconvolution which was

Basically there is a class visualize. You can initialize the class using any pretrained networks which are available in pytorch.

     model=models.alexnet(pretrained=True)

     device=torch.device("cuda" if torch.cuda.is_available() else "cpu")
     
     v=visualize(model, device)
Here I am using alexnet, any other network like suppose vgg16 can be passed.
#### There are 2 methods callable methods:
### Method 1:visualize:
### Method 2:construct:

## References
[Zeiler and Fergus(DeconvNet)](https://arxiv.org/abs/1311.2901)
