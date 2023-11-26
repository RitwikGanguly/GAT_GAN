# GAT GAN

---

# Index of the Document

| Topics in Project | 
|--|
| 1. [Description of the Project](#project-description) | 
| 2. [Regression Techniques](#regression-techniques--concepts-) | 
| 3. [Classification Techniques](#classification-techniques--concepts-) | 
| 3.1 [Support Vector Machines](#support-vector-machine-svm) | 
| 3.2 [Decision Tree](#decision-tree-concepts) | 
| 3.2 [Boosting( GBM, Light GBM, CatBoost)](#boosting-algorithms-gbm-lightgbm-catboost) | 
| 3.2 [Naive Bayes Classifier](#naive-bayes-classifier) | 
| 4. [Stats & probabality](#stats--probablity-fundamentals) | 
| 5. [Deep Learning Fundamentals](#deep-learning-fundamentals)| 
| 5.1 [CNN](#cnn-fundamentals--cost-function-backpropagation) | 
| 6 [Attention & Transformers](#deep-learning---nlp) | 

## Project Title: Subsampling and Data Generation for Single-Cell Clustering using GAT-GAN
## Project Description: 
In this project, we aim to enhance the efficiency and utility of single-cell DNA sequencing data by employing a two-step process. 
First, we perform subsampling using Graph Attention Networks (GAT) to select a representative set of nodes with lesser number of sample value counts from the initial sample nodes in the dataset(i.e. Yan Data:In this data we have 90 samples and 10564 features, after doing subsampling using GAT we got 12 nodes and after we will be using these nodes for data generation), ensuring minimal value counts. This step helps reduce data complexity and dimensionality while preserving essential information.

Next, we employ Generative Adversarial Networks (GANs) to generate new data points based on the subsampled dataset. These generated data points expand the dataset, enabling more comprehensive analysis and improving the robustness of single-cell clustering.

This methodology is not limited to a single dataset(i.e. Yan Dataset) but can be applied to various single-cell clustering datasets, enhancing the scalability and versatility of our approach. The final output includes both the subsampled dataset and the generated data, paving the way for more effective single-cell clustering analysis in genomics research.

---
# GAT-GAN Model for single Cell Clustering

<!--## Single-Cell Clustering

### Overview

Single-cell clustering is a computational technique applied in genomics to analyze single-cell RNA sequencing (scRNA-seq) data. This method groups individual cells into clusters based on gene expression profiles, aiding in the identification of cell types and states.

### Key Steps

1. **Data Preprocessing:**
   - Remove noise, correct artifacts, and normalize expression values in raw scRNA-seq data.

2. **Dimensionality Reduction:**
   - Utilize techniques like PCA, t-SNE, or UMAP to reduce dimensionality and visualize relationships between cells.

3. **Clustering Algorithms:**
   - Employ K-means, hierarchical clustering, density-based methods (e.g., DBSCAN), or graph-based methods (e.g., Graph Attention Networks) for grouping cells.

4. **Visualization:**
   - Visualize results using t-SNE plots, UMAP plots, or other techniques to explore relationships between different cell clusters.

### Applications

- **Cell Type Identification:**
  - Single-cell clustering helps identify distinct cell types within a heterogeneous tissue. This is crucial for understanding the cellular composition of organs and tissues.

- **Disease Subtyping:**
  - Clustering can reveal disease-specific cell subpopulations, aiding in the identification of subtypes and potential biomarkers for diseases such as cancer

- **Developmental Biology:**
  - Studying gene expression at the single-cell level allows researchers to track cell differentiation and developmental processes, providing insights into tissue development.

- **Immunology:**
  - Identifying different immune cell populations helps in understanding immune responses, discovering rare cell types, and characterizing immune cell heterogeneity.

- **Drug Discovery:**
  - Identify target cells, understand cellular responses, and uncover potential drug resistance mechanisms.

- **Rare Cell Identification:**
  - Detecting and characterizing rare cell populations, which may be crucial in understanding diseases or uncovering unique cellular functions. 
  -->

## Generative Adversarial Network (GAN)

### Overview

Generative Adversarial Networks (GANs) are a class of algorithms used in unsupervised machine learning. Consisting of a generator and a discriminator, GANs generate synthetic data while distinguishing it from real data through adversarial training.

### Key Components

1. **Generator:**
   - The generator is a crucial component of a GAN. It is a neural network responsible for creating synthetic data that resembles the training data.
Input to the generator is typically random noise or a random vector. The generator then transforms this noise into data that ideally cannot be distinguished from real data.
The quality of the generated data is improved iteratively through training.


2. **Discriminator:**
   - The discriminator is another neural network that acts as a binary classifier. Its role is to distinguish between real data from the training set and synthetic data produced by the generator.
The discriminator assigns a probability to each input, indicating the likelihood that it belongs to the real dataset.
During training, the discriminator's objective is to correctly classify real and synthetic samples, while the generator's objective is to generate data that is indistinguishable from real data.

3. **Training Process:**
   - The generator and discriminator are trained in a competitive manner. As the generator improves, the discriminator must adapt to the increasingly realistic synthetic data.
This adversarial training process continues until an equilibrium is reached, ideally resulting in a generator that produces high-quality synthetic data.

4. **Adversarial Loss:**
   - The training involves minimizing the loss for both the generator and discriminator. The generator's loss depends on its ability to fool the discriminator, while the discriminator's loss depends on its accuracy in distinguishing real and synthetic samples.

### Applications

- **Image Synthesis:**
  - GANs have been widely used to generate realistic images, including faces, objects, and scenes.
Applications range from creating high-resolution artwork to generating diverse datasets for training machine learning models.

- **Style Transfer:**
  - GANs can transfer artistic styles from one image to another, allowing for creative transformations.
This application is often used in the fields of art and design for producing unique visual outputs

- **Image-to-Image Translation:**
  - GANs enable the transformation of images from one domain to another, such as turning satellite images into maps or converting black-and-white photos to color.
This has applications in augmented reality, image enhancement, and domain adaptation.

- **Data Augmentation:**
  - GANs can generate synthetic data to augment training datasets, improving the robustness and generalization of machine learning models.
This is particularly useful in scenarios where obtaining large labeled datasets is challenging.

## Graph Attention Networks (GAT)

### Overview

Graph Attention Networks (GAT) are neural network architectures designed for processing graph-structured data, excelling in tasks like node classification and link prediction.

### Key Features

1. **Attention Mechanism:**
   - GAT uses attention mechanisms to allow nodes to weigh the importance of neighboring nodes differently during the learning process.
This attention mechanism enables GAT to capture complex relationships within the graph, giving more weight to relevant nodes.

2. **Node-Level Representations:**
   - GAT learns node-level representations, capturing intricate relationships in graph-structured data.
The model produces embeddings that reflect the characteristics of nodes and their connections.

3. **Versatility:**
   - Applicable to various domains, including social network analysis, citation networks, and biological network analysis.
In the context of biology, GAT can be applied to study protein-protein interaction networks or gene co-expression networks.

### Applications

- **Biological Network Analysis:**
  - Analyze protein-protein interaction networks and gene regulatory networks.

- **Drug-Target Interaction Prediction:**
  - Predict interactions between drugs and target proteins.

- **Social Network Analysis:**
  - Model social networks to identify influential individuals and detect communities.

- **Recommendation Systems:**
  - Apply in recommendation systems to model user-item interactions.

- **Fraud Detection:**
  - Employed in fraud detection scenarios for accurate detection based on complex relationships.

---

## Adjusted Rand Index (ARI)

### Overview

The Adjusted Rand Index (ARI) is a metric used to evaluate the similarity between two clusterings, adjusting for chance agreement.

### Advantages

- Accounts for chance in random clustering scenarios.
- Ranges from -1 to 1, indicating complete disagreement to perfect agreement.

### Use Cases

- Evaluate clusters in machine learning.
- Compare different clustering algorithms.

## Wasserstein Distance

### Overview

Wasserstein distance, or Earth Mover's Distance, measures the minimum "cost" to transform one probability distribution into another.

### Advantages

- Efficient for comparing distributions that may not align perfectly.
- Captures spatial relationships in distributions.

### Limitations

- Provides an approximation to similarity and may not guarantee exact results.

### Use Cases

- Compare probability distributions in statistics.
- Apply in image processing and machine learning.

## UMAP Visualization

### Overview

Uniform Manifold Approximation and Projection (UMAP) is a dimensionality reduction technique for visualizing high-dimensional data.

### Key Features

1. **Dimensionality Reduction:**
   - Reduces high-dimensional data while preserving underlying structure.

2. **Preservation of Local and Global Structure:**
   - Captures both local and global relationships in the data.

3. **Versatility:**
   - Applicable to various data types, including biological and image data.

4. **Scalability:**
   - Efficient and scalable to large datasets.

### Implementation

- Implemented in Python, commonly using the "umap-learn" library.

### Use Cases

- Exploratory data analysis.
- Pattern recognition in high-dimensional datasets.











---

---

<h2 align="center">Behind this Work</h2>

<div style="display: flex; justify-content: space-between; align-items: center;">
  
  <div align="center">
    <img src="https://scontent.fccu11-1.fna.fbcdn.net/v/t39.30808-6/385860305_731250479017131_3309006476143941761_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=49d041&_nc_ohc=pAQRMcLIF18AX_Sdn5C&_nc_ht=scontent.fccu11-1.fna&oh=00_AfA4Kga6xbjTKivPPXQjrR_4Iimz3SetN3Pb6fFmB4IO5A&oe=6520ADBA" height="200" alt="Developer 1" width="175">
    <p><b>Ritwik Ganguly</b></p>
    <p align="center">
    <a href="https://www.linkedin.com/in/ritwikganguly003/" target="blank"><img align="center" src="https://www.svgrepo.com/show/110195/linkedin.svg" alt="ritwik-ganguly-148aa2203" height="30" width="40" /></a>
    <a href="https://medium.com/@gangulyritwik2003" target="blank"><img align="center" src="https://www.svgrepo.com/show/354057/medium-icon.svg" alt="ritwik-ganguly-148aa2203" height="30" width="40" /></a>
    <a href="https://github.com/RitwikGanguly" target="blank"><img align="center" src="https://www.svgrepo.com/show/512317/github-142.svg" alt="ritwik" height="30" width="40" /></a>
    </p>
  </div>
  <div align="center">
    <img src="https://scontent.fccu2-3.fna.fbcdn.net/v/t1.6435-9/166272161_237885504724949_22398833292288906_n.jpg?_nc_cat=102&ccb=1-7&_nc_sid=09cbfe&_nc_ohc=ITmqhdTSQUIAX81zio9&_nc_ht=scontent.fccu2-3.fna&oh=00_AfAgnbzegfmEiRgn0lMnE4PNqsVBsstAO8Sv2BXyyLc_nQ&oe=653B4219" height="200" alt="Developer 2" width="200">
    <p><b>Nilanjana Bhattacharya</b></p>
    <p align="center">
    <a href="https://www.linkedin.com/in/nilanjana-bhattacharya-270007263/" target="blank"><img align="center" src="https://www.svgrepo.com/show/110195/linkedin.svg" alt="ritwik-ganguly-148aa2203" height="30" width="40" /></a>
    <a href="https://medium.com/@gangulyritwik2003" target="blank"><img align="center" src="https://www.svgrepo.com/show/354057/medium-icon.svg" alt="ritwik-ganguly-148aa2203" height="30" width="40" /></a>
    <a href="https://github.com/RitwikGanguly" target="blank"><img align="center" src="https://www.svgrepo.com/show/512317/github-142.svg" alt="ritwik" height="30" width="40" /></a>
    </p>
  </div>
  
  <div align="center">
    <img src="https://media.licdn.com/dms/image/D4D03AQEaz1a6yN2fmw/profile-displayphoto-shrink_800_800/0/1679486077155?e=1701302400&v=beta&t=Ns7pru7F3j4GicZewd3upyHQ_mUzHUhskMLioaxOYV4" height="200" alt="Developer 3" width="200">
    <p><b>Sruti de</b></p>
    <p align="center">
    <a href="https://www.linkedin.com/in/ritwikganguly003/" target="blank"><img align="center" src="https://www.svgrepo.com/show/110195/linkedin.svg" alt="ritwik-ganguly-148aa2203" height="30" width="40" /></a>
    <a href="https://medium.com/@gangulyritwik2003" target="blank"><img align="center" src="https://www.svgrepo.com/show/354057/medium-icon.svg" alt="ritwik-ganguly-148aa2203" height="30" width="40" /></a>
    <a href="https://github.com/RitwikGanguly" target="blank"><img align="center" src="https://www.svgrepo.com/show/512317/github-142.svg" alt="ritwik" height="30" width="40" /></a>
    </p>
  </div>
  
</div>
