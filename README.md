# AutoEncoder-CBIR
using autoencoder for Content-based Image Retrieval 

## DISCRIPTION
> Deep learning-based CBIR and image retrieval can be framed as a form of unsupervised learning:
> 
  * When training the autoencoder, we do not use any class labels
  * The autoencoder is then used to compute the latent-space vector representation for each image in our dataset (i.e., our “feature vector” for a given image)
  * Then, at search time, we compute the distance between the latent-space vectors — the smaller the distance, the more relevant/visually similar two images are
>
> we’ll compute feature vectors for each image in our dataset. Computing the feature vector for a given image requires only a forward-pass of the image through the network — the output of the encoder (i.e., the latent-space representation) will serve as our feature vector.After all images are encoded, we can then compare vectors by computing the distance between them. Images with a smaller distance will be more similar than images with a larger distance.
> 
## DATASET
> we’ll be training an autoencoder on the MNIST dataset. The MNIST dataset consists of digits that are 28×28 pixels with a single channel, implying that each digit is represented by 28 x 28 = 784 values.
> 





















































## License
> [Autoencoders for Content-based Image Retrieval with Keras and TensorFlow](https://www.pyimagesearch.com/2020/03/30/autoencoders-for-content-based-image-retrieval-with-keras-and-tensorflow/) by Adrian Rosebrock
