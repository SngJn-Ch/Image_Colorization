# Image_Colorization
  1. Colorize Black and White image
  2. The image size is 96*96


# Layer Explanation

  # Generator and Discriminator
  
  Use Autoencoder bottleneck layer shape for the generator. 
  
  **Green block "F64K2S2" is Convolution layer with filter size of 64, kernel size of 2, strides of 2 and follwed by BatchNormalization and LeakyReLU**
  
 **Blue Block is normal Convoluation 2D layer**
 
 **Orange block is Dense layer with a filter size on it. Each of the Dense layer with size of 1024 and 1 are followed by LeakyReLU, and sigmoid activation.**
  
  <img src="https://user-images.githubusercontent.com/111392592/188504365-ea1a257b-126d-49c5-9859-92f896389f7c.png" width = "300" height = "600">

  
  
  
 # Loss Function
 
  1. **MeanSquaredError** of real image and fake image -  **actual_diff**
  2. Content loss from **MeanSquaredError** output of Resnet50 layer of real image and fake image(transfer learning) - **content loss**
  3. **BinaryCrossEntropy** result of reak unage abd fake image. - **g_loss**
  
    3-1. real image as 1
    
    3-2. fake image as 0
    
  Formula
  
  10*actual_diff + 0.01*content_loss + 0.001*g_loss
     

# Result

left: Gray image input

middle: Output image

Right: actual image


![190](https://user-images.githubusercontent.com/111392592/188255449-183a4c7d-5b7e-4eca-9acd-7ff0ab756453.png)

![180](https://user-images.githubusercontent.com/111392592/188255581-87bd70aa-3853-4b6c-a711-6cc987256742.png)

![180 (1)](https://user-images.githubusercontent.com/111392592/188256181-781eaea4-2fc2-4422-84d5-d8164ebac4c9.png)


# Checkpoint
  
  https://drive.google.com/drive/folders/1tO9RQn7qHs1r6lCYVD00hJDvCZ-Qfh_1?usp=sharing
  
  
# Future Improvement

  1. The image colorization of the images with people can be improved by introducing extra FFHQ dataset.
  2. Current resolution is 96*96, find out how to colorize high resolution images within given resources(Google Colab Pro)
  
  
# Reference

  #Data
  2013 Dataset from Imagenet
  
    https://www.image-net.org/
    
    
  Concept of autoencoder and its bottleneck layer shape
  
    https://www.tensorflow.org/tutorials/generative/autoencoder
  
