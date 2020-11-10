# AnimeCharacterDCGANGeneration
 DCGAN model to generate Anime Characters

## Background
Anime is Japanese art style for drawing and animating cartoon characters. It is discerned by characters with voluminous and colorful hair, accentuated eyes, small noses, and large faces. “Towards the Automatic Anime Characters Creation with Generative Adversarial Networks” from Jin et al. presents a novel approach to program various GAN models to generate anime characters. Jin and others have executed SQL queries to download images of characters from Getchu, a proprietary website for information on Japanese games. Utilizing a face detector known as “lbpcascade animeface”, each image was bounded to crop only faces. With 42000 images collected for the dataset, images were manually checked and removed for undesired attributes.

## Methodology
10000 iterations were used to train the DCGAN model. The batch size of 64 remains the same but the learning rate is increased to 0.0004 as there are fewer iterations to train the dataset. Moreover, a weight decay value of 1e-8 was applied to prevent the weights from growing too large. The DCGAN model also incorporates generated random noise using normal distribution to its input labels to improve the performance of the discriminator. For each epoch, the anime image created by the generator and the binary cross entropy losses of both the discriminator and the generator are plotted. Figure 2 shows a sequential progression of the generation of images along with respective losses of the components for that epoch. The duration of training for 10000 iterations was around 4 hours in the Google Colab environment. 

## Results

For 10000 iterations, the generator creates distinguishable anime character faces with low generator and discriminator loss. The generator shows best performance in creating believable anime facial structures, noses, hair, and hair color. However, in some of the images, the eyes are often blurred due to training loss and the irises of the eyes are slightly different color shades from each other.

## Scope

1) The features of the anime faces are refined and distinguishable with longer hair of various colors and large faces with small prominent chins. 
2)However, in many of the images, the generator struggles to produce eyes of the same color with minimal blurring. To alleviate these issues in the future, training on the DCGAN can be done for a larger number of iterations or the convolutional blocks can be replaced with residual blocks that utilize skip connections to minimize loss.
