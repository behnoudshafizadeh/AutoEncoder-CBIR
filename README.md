# AutoEncoder-CBIR
using autoencoder for Content-based Image Retrieval 

## DISCRIPTION
> Deep learning-based CBIR and image retrieval can be framed as a form of unsupervised learning:
> 
>  * When training the autoencoder, we do not use any class labels
>  * The autoencoder is then used to compute the latent-space vector representation for each image in our dataset (i.e., our “feature vector” for a given image)
>  * Then, at search time, we compute the distance between the latent-space vectors — the smaller the distance, the more relevant/visually similar two images are
>
> we’ll compute feature vectors for each image in our dataset. Computing the feature vector for a given image requires only a forward-pass of the image through the network — the output of the encoder (i.e., the latent-space representation) will serve as our feature vector.After all images are encoded, we can then compare vectors by computing the distance between them. Images with a smaller distance will be more similar than images with a larger distance.
> 
## DATASET
> we’ll be training an autoencoder on the MNIST dataset. The MNIST dataset consists of digits that are 28×28 pixels with a single channel, implying that each digit is represented by 28 x 28 = 784 values.
> 
## STRUCTURE of This Project
> this project has 3 `.py` files as below:
>
> * `train_autoencoder.py`: Trains an autoencoder on the MNIST handwritten digits dataset using the ConvAutoencoder CNN/class
> * `index_images.py`: Using the encoder portion of our trained autoencoder, we’ll compute feature vectors for each image in the dataset and add the features to a searchable index
> * `search.py`: Queries our index for similar images using a similarity metric
>
> Our `output` directory contains our trained autoencoder and index. Training also results in a training history plot and visualization image that can be exported to the `output` directory.
> 
## Training Procedure
> the architecture of autoencdoer is in `pyimagesearch/convautoencoder.py` and for starting the train procedure you can run following command:
```
python train_autoencoder.py --model output/autoencoder.h5 --vis output/recon_vis.png --plot output/plot.png
```
> after running this cell, the result of train/validation basis on our dataset will be creating,such as below :
>
![plot](https://user-images.githubusercontent.com/53394692/111424036-6fca1400-8706-11eb-9ac3-13241562f814.png)
> Furthermore, the following reconstruction plot shows that our autoencoder is doing a fantastic job of reconstructing our input digits.such as below:
![recon_vis](https://user-images.githubusercontent.com/53394692/111424138-95571d80-8706-11eb-8ff2-7b0ad9767fcc.png)
>
## Implementing image indexer using the trained autoencoder
> This phase requires us to use our trained autoencoder (specifically the “encoder” portion) to accept an input image, perform a forward pass, and then take the output of the encoder portion of the network to generate our index of feature vectors. These feature vectors are meant to quantify the contents of each image.so run the bellow command :
```
python index_images.py --model output/autoencoder.h5 --index output/features.pickle
```
> * `--model`: The trained autoencoder input path from the previous step
> * `--index`: The path to the output features index file in .pickle format
>
## Implementing the image search and retrieval script
```
python search.py --model output/autoencoder.h5 --index output/index.pickle
```
> so,as a result you will see result as below which is an  example providing a query image containing the digit `9`  along with the search results from our autoencoder image retrieval system :
> 
| sample  | CBIR-System (output) | 
| ----------- | -------- | 
| ![sample1](https://user-images.githubusercontent.com/53394692/111425779-e405b700-8708-11eb-8e31-1cbe0c013804.PNG) | ![sample2](https://user-images.githubusercontent.com/53394692/111425819-f3850000-8708-11eb-9c66-edcc36c56fb1.PNG) | 
>
## License
> [Autoencoders for Content-based Image Retrieval with Keras and TensorFlow](https://www.pyimagesearch.com/2020/03/30/autoencoders-for-content-based-image-retrieval-with-keras-and-tensorflow/) by Adrian Rosebrock
