[<---   6__Prediction.md](6__Prediction.md)         [Зміст](README.md)          [6_2_Image_classification.md    --->](6_2_Image_classification.md) 

## 6.1    Image denoising

A direct application of deep models to image processing is to recover from degradation by utilizing the redundancy in the statistical structure of images. The petals of a sunflower on a grayscale picture can be colored with high confidence, and the texture of a geometric shape such as a table on a low-light grainy picture can be corrected by averaging it over a large area likely to be uniform.

A **denoising autoencoder** is a model that takes as input a degraded signal $\tilde{X}$ and computes an estimate of the original one $X$. For images, it is a convolutional network that may integrate skip-connections, in particular to combine representations at the same resolution obtained early and late in the model, and attention layers to facilitate taking into account elements far away from each other.

Such a model is trained by collecting a large number of clean samples paired with their degraded inputs. The latter can be captured in degraded conditions, such as low-light or inadequate focus, or generated algorithmically, for instance, by converting the clean sample to grayscale, reducing its size, or compressing it aggressively with a lossy compression method. 

The standard training procedure for denoising autoencoders uses the MSE loss summed across all pixels, in which case the model aims at computing the best average clean picture, given the degraded one, that is $E(X|\tilde{X} )$. This quantity may be problematic when $X$ is not completely determined by $\tilde{X}$ , in which case some parts of the generated signal may be an unrealistic, blurry average.

