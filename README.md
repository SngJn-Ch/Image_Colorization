# Image_Colorization
Colorize Black and White image
ImageSize = 96*96

# Layer Explanation

  # Generator
  
  Use Autoencoder bottleneck layer shape for the generator. 
  
  Green block "F64K2S2" is Convolution layer with filter size of 64, kernel size of 2, strides of 2 and follwed by BatchNormalization and LeakyReLU
  
 Blue Block is normal Convoluation 2D layer  
 
 Orange block is Dense layer with a filter size on it. Each of the Dense layer with size of 1024 and 1 are followed by LeakyReLU, and sigmoid activation.
  
  <img src="https://user-images.githubusercontent.com/111392592/188255177-025f8ab1-65c4-4d23-9701-10c3fea43277.png" width = "90">

 
  # Discriminator
  
  <img src="https://user-images.githubusercontent.com/111392592/188255264-d87851b1-2a25-4940-bbc6-5c466a5b0bd8.png" width = "90">
  
  
 # Loss Function
 
  1. MeanSquaredError of real image and fake image - actual_diff
  2. Content loss from output of Resnet50 layer of real image and fake image - content loss
  3. BinaryCrossEntropy result of reak unage abd fake image. - g_loss
    3-1. real image as 1
    3-2. fake image as 2
    
  Formula
  
  10*actual_diff + 0.01*content_loss + 0.001*g_loss
    
