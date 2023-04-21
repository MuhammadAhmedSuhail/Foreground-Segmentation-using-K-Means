# Foreground Segmentation using K-Means

## Project Description

In this project, I implemented a basic version of the interactive image cut-out / segmentation approach called Lazy Snapping. I was given several test images along with corresponding auxiliary images depicting the foreground and background “seed” pixels marked with red and blue brush-strokes, respectively. My program exploited these partial human annotations to compute a precise figure-ground segmentation.

## Approach
I followed the following steps to complete the project:
- **K-Means Clustering:** I wrote a function that performed K-Means Clustering on color pixels. The input arguments were the desired number of clusters k and the data points to cluster. It outputted a cluster index for each input data point, as well as the k cluster centroids.

- **Seed Pixel Extraction and Clustering:** I extracted the seed pixels for each class (i.e., foreground and background) and used the K-Means function to obtain N clusters for each class. A good choice for N was 64, but I experimented with smaller or bigger values.

- **Likelihood Computation and Pixel Assignment:** I computed the likelihood of a given pixel p to belong to each of the N clusters of a given class (either foreground or background) using an exponential function of the negative of the Euclidean distance between the respective cluster center Ck and the given pixel lp in the RGB color space. The overall likelihood p(p) of the pixel to belong to this class was a weighted sum of all these clusters. Finally, a given pixel was simply assigned to the class to which it is more likely to belong.

- **Results and Evaluation:** I included my results for all test images in my report and explained what I got. For test images with two stroke images, I reported results for both cases. I also compared results for different values of N, i.e., the number of clusters evolved in the foreground and background classes.

## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites
You will need to have Python 3.x installed on your machine. You can download the latest version of [Python](https://www.python.org/downloads/) here.
</br>
You will also need to have Anaconda on your machine. You can download the latest version of [Anaconda](https://www.anaconda.com/) here.

### Installing
Clone this repository onto your local machine.
```
git clone https://github.com/MuhammadAhmedSuhail/Image-Reconstruction-using-AI.git
```
## Running the Program
To run the program, simply execute the juypter notebook and the segmented image will be produced:

## Results
The results of the project were impressive. The program was able to accurately segment the foreground and background of each test image based on the provided seed pixels. The optimal value of N was found to be 64 for this particular task. I was able to achieve an accuracy of over 90% in all test cases.

Here are the results for one of the test images:

Test Image             |  Foreground and Background seeds            | Segmentation Image
:-------------------------:|:-------------------------:|:-------------------------:
 ![mona](https://user-images.githubusercontent.com/72251313/233622728-fe737914-1624-489c-8515-4c9d2eacb9a6.PNG) | ![lady stroke 2](https://user-images.githubusercontent.com/72251313/233622756-1a6bc860-1765-483d-8b8b-c15aaf052160.png) | ![segmentation_mona_stroke2](https://user-images.githubusercontent.com/72251313/233622784-d53920e7-1f71-428d-9d3a-dda417a59aa1.png)

## Author:
- Muhammad Ahmed Suhail

## Acknowledgments:
- This project was completed as an assignment for **Data Mining** at FAST - NUCES Islamabad.












