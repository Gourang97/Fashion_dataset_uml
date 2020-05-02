# Image-based Product Recommendation System [An Unsupervised Way]

<br/><center><img src="https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/FirstSlide.PNG" width="600" height="400"></center>

## Idea
Current implementations of image recommendations are used by giant e-commerce portals like
Amazon, Alibaba, etc but still stand inefficient in the sense they require user text input. We, on
the other hand, intend to optimize the whole system by taking images as input from the user.
This would enhance the customer experience and fill up the gaps faced in text searches

## Problem Statement
Develop an image-based product recommendation system used primarily in the e-commerce
domain. This engine will take as input an image of a certain product and recommend 5 similar
products that resemble closely to the input image. We aim to achieve this goal by implementing
a combination of dimensionality reduction, clustering, modelling and recommendation system
techniques.

## Dataset

The fashion industry is one of the most prominent parts of the e-commerce industry and has
tons of data publicly available. We decided to use the [Fashion Product Image dataset](https://www.kaggle.com/paramaggarwal/fashion-product-images-dataset) for our
project. It’s a rich dataset of product features and images spread across 7 master categories, 49
subcategories, and 143 article types. Each product has a unique id to distinguish them.
The dataset can broadly be divided into image data and style data. The data is described as
follows:
1. Image data: Each image has a unique id and is of size 2400*1800*3. All the images
have a clear white background with the object in the foreground.

2. Style data: The styles.csv contains metadata about the image. Analysis of various fields
like ‘gender’, ‘masterCategory’, ‘subCategory’, ‘articleType’ tells us about the distribution
of the data.

The dataset is highly imbalanced across the different article types. To overcome this
shortcoming, we started our implementation by taking into account the top 5 article type and
verifying it through a thorough analysis of the product features. The article types which we
finalized are: T-shirts, Shirts, Casual Shoes, Watches and Sports Shoes. We used 1000 images
of each article type. Considering the problem statement and the practical nature of the project,
we implemented an Image Data Generator to perform image augmentation by rotating and
capturing images through 4 different angles. The new augmented dataset consisted of 5000
images for each of the 5 article types.

## Steps Involved for Building Recommender System in an Unsupervised Way- 
- Data Loading
- Selecting optimum dimensions to be used using Scree and Elbow Plot.
- Dimensionality Reduction
   1. PCA on original Image
   2. PCA on image with Reduced dimesnions
   3. TSNE on original image
   4. TSNE on image with Reduced dimensions
- Selecting optimum Cluster uing SSE Plot
- Clustering -
    1. KMeans
    2. Gaussian Mixture Model
    3. Agglomerative Clustering
 - Select Best Clusterting technique to be used
 - Use Distance metrices to Recommend Images
    1. Cosine Similarity
    2. Spatial Distances
 
 ## Results-
 - Selecting optimum dimensions to be used using Scree and Elbow Plot.[https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/elbow_curve_tshirts.png]
 
<b>- Dimensionality Reduction</b>
1. PCA on original Image
   <br/><center><img src="https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/pca_original.png" width="400" height="200"></center>
2. TSNE on original image
   <br/><center><img src="https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/tsneOriginal.png" width="400" height="200"></center>
- Selecting optimum Cluster uing SSE Plot
<br/><center><img src="https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/elbow_curve_shoes.png" width="400" height="200"></center>

<b>- Clustering -</b>
1. KMeans
1.1 PCA Results

* [KMeans with PCA]
    <br/><center><img src="https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/kmeans/pcaKmeans.png" width="400" height="200"></center>
    
1.2 TSNE Results

 * [KMeans with TSNE]
    <br/><center><img src="https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/kmeans/tsneKMeans.png" width="400" height="200"></center>
2. Gaussian Mixture Model

2.1 PCA Results

* [GMM with PCA]
    <br/><center><img src="https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/GMM/pcaGmm.png" width="400" height="200"></center>
    
2.2 TSNE Results

* [GMM with TSNE]
    <br/><center><img src="https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/GMM/tsneGmm.png" width="400" height="200"></center>
    
<b> 3. Agglomerative Clustering </b>

3.1 PCA Results

* [AGG with PCA]
    <br/><center><img src="https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/AGG/pcaAggWard.png" width="400" height="200"></center>
    
3.2 TSNE Results

* [AGG with TSNE]
    <br/><center><img src="https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/AGG/aggTSNE.png" width="400" height="200"></center>
    
<b>- Select Best Clusterting technique to be used</b>

<br/><center><img src="https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/ClusterComparison.PNG"></center>

<b>- Use Distance metrices to Recommend Images</b>
    
<b>-Cosine Similarity and Spatial Distances</b>

We finally recommend 5 similar images for every product entered as input @e-commerce by the user using best output from spatial or cosine similarity metrics.

<br/><center><img src="https://github.com/Gourang97/Fashion_dataset_uml/blob/master/Results/final_result_recommed.PNG"></center>
 
 
   
  
