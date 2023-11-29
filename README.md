# Deep learning-based characterization of neutrophil activation phenotypes in ex vivo human Candida blood infections

### Abstract
The early identification of human pathogens is crucial for the effective treatment of bloodstream infections to prevent sepsis. Since pathogens that are present in small numbers are usually difficult to detect directly, we hypothesize that the behavior of the immune cells that are present in large numbers may provide indirect evidence about the causative pathogen of the infection. We previously applied time-lapse microscopy to observe that neutrophils isolated from human whole-blood samples, which had been infected with the human-pathogenic fungus Candida albicans or C. glabrata, indeed exhibited a characteristic morphodynamic behavior. Tracking the neutrophil movement and shape dynamics over time combined with a white-box machine learning approach allowed us to distinguish the infected whole-blood samples from pathogen-free control samples with 100% accuracy. However, based on features like morphodynamics and intensity gradient of neutrophils, the accuracy for the differentiation between the two Candida species was significantly reduced to about 75%. In this study, the focus is on improving the classification accuracy of the Candida species using a black-box approach in terms of advanced deep learning methods. We implemented (i) gated recurrent unit (GRU) networks and transformer-based networks for video data, and (ii) convolutional neural networks (CNNs) for individual frames of the time-lapse microscopy data. While the GRU and transformer-based approaches yielded promising results with 96% and 100% accuracy, respectively, the classification based on videos proved to be very time-consuming and required several hours. In contrast, the CNN model for individual microscopy frames yielded results within minutes, and, utilizing a majority-vote technique, achieved 100% accuracy both in identifying the pathogen-free blood samples and in distinguishing between the Candida species. We conclude that the applied CNN demonstrates the potential for automatically differentiating bloodstream Candida infections from individual microscopy frames with high accuracy and efficiency. We further analysed the results of the trained CNN using explainable artificial intelligence (XAI) techniques to understand the critical features and patterns the network was focusing on, thereby shedding light on potential key morphodynamic characteristics of neutrophils in response to different Candida species. This approach could provide new insights into host-pathogen interactions and may facilitate the development of rapid, automated diagnostic tools for differentiating fungal species in blood samples, ultimately contributing to faster and more targeted therapeutic interventions.

This repository contains Python code supporting our research on automated classification of neutrophil images in various infection scenarios using deep learning models. Our work utilizes a unique dataset derived from whole blood infection (WBI) samples to analyze neutrophil behavior under different conditions.

### Repository Structure
The repository is organized into five directories, each corresponding to a specific aspect of our research:

### Transformers on Cell Track Videos: 
Contains code for the transformer-based classification of single-cell morphodynamics videos.

### Transformers and GRU on Patch Videos: 
Includes code for our hybrid models combining CNNs with either GRUs or Transformers for classifying neutrophil behavior in video patches.

### CNN on Original Images: 
This directory hosts code for CNN-based classification using unprocessed original images from our dataset.

### CNN on Preprocessed Images: 
Contains code for CNN models trained on images that underwent pre-processing steps such as Gaussian blur, CLAHE, and unsharp masking.

### CNN on Preprocessed Patches: 
Features code for CNN models trained on patches extracted from pre-processed images, aiming to enhance dataset size and variability.

### Dataset Overview
The dataset consists of 27 time-lapse microscopy videos, each providing 260 images (2048 x 2048 pixels) captured every 7 seconds over 30 minutes. These images were derived from blood samples of nine healthy donors, each subjected to three different infection scenarios for comprehensive analysis.

### Preprocessing Steps
We applied several preprocessing steps to the images to correct disparities in brightness and contrast across different donors. These steps included applying Gaussian blur, blending with original images, CLAHE, unsharp masking, and pixel value clipping.

### Methodology
Our approach encompasses various deep learning techniques:

Transformers and GRUs: We employed transformers and GRUs to analyze the temporal and spatial characteristics of neutrophils in video data.
CNNs on Images: We explored the efficiency of CNNs in classifying neutrophil images and videos, comparing models trained on original, preprocessed, and patch-based images.

### Requirements
Python 3.x
Libraries: OpenCV, scikit-image, TensorFlow, NumPy, patchify

