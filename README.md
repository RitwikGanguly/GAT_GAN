# GAT GAN

---

# Index of the Document

| Topics in Project | 
|--|
| 1. [Description of the Project](#project-description) | 
| 2. [GAN](#generative-adversarial-network) | 
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

## Generative Adversarial Network

---

**GAN is an unsupervised deep learning algorithm where we have a Generator pitted against an adversarial network called Discriminator.**

**Generator generates counterfeit currency. Discriminators are a team of cops trying to detect the counterfeit currency. Counterfeiters and cops both are trying to beat each other at their game.**

![Gan Image](https://miro.medium.com/v2/resize:fit:828/format:webp/1*t78gwhhw-hn1CgXc1K89wA.png)

Generator’s objective will be to generate data that is very similar to the training data. Data generated from Generator should be indistinguishable from the real data.

Discriminator takes two sets of input, one input comes from the training dataset(real data) and the other input is the dataset generated by Generator.

**Generator:**
The generator's main role is to create realistic data samples that are similar to the training data. It takes random noise as input and gradually transforms it into data samples that should resemble real data. The generator's architecture is typically a deep neural network, often constructed using layers like fully connected (dense) layers or convolutional layers in the case of images. The generator starts with random noise and progressively refines it through multiple layers to generate more complex and coherent samples.


**Discriminator:**
The discriminator's primary task is to distinguish between real data samples from the training dataset and fake samples generated by the generator. Like the generator, the discriminator is also a deep neural network. It takes input data (either real or fake) and produces a probability score indicating whether the input is real or fake. The discriminator's architecture is similar to that of a binary classifier, aiming to learn to differentiate between real and fake samples effectively.


**Training Process:**
- Generator Training: Initially, the generator produces fake data samples using random noise as input. These fake samples are then passed to the discriminator for evaluation.


- Discriminator Training: The discriminator receives both real data samples from the training set and fake samples from the generator. It is trained to correctly classify real samples as real (label 1) and fake samples as fake (label 0).

**Loss Functions:**
- **Generator Loss:** The generator's objective is to create samples that are convincing enough to fool the discriminator. To achieve this, the generator aims to minimize the difference between the discriminator's predictions on fake samples and the desired label (1, indicating real). In other words, the generator's loss function encourages it to produce samples that the discriminator thinks are real.


- **Discriminator Loss:** The discriminator's goal is to accurately classify real and fake samples. Its loss function involves a combination of the errors made on real and fake samples. The goal is to maximize the difference between its predictions on real and fake samples.

**Minimax Game:**

The training process can be understood as a minimax game where the generator and discriminator are engaged in adversarial training. The generator updates its parameters to minimize its loss while the discriminator updates its parameters to maximize its accuracy in distinguishing real from fake samples. This process leads to a dynamic equilibrium where the generator produces more realistic samples as the discriminator becomes better at its task.


### GAN Loss Functions

In a Generative Adversarial Network (GAN), there are two primary loss functions: one for the generator and another for the discriminator.

**Generator Loss (L<sub>G</sub>)**

The goal of the generator is to produce data samples that are indistinguishable from real data. The generator loss is calculated based on the discriminator's classification of the generated samples. It can be expressed as the negative log likelihood of the discriminator being mistaken about the generated samples:

![Generator Loss](https://latex.codecogs.com/svg.image?L_G&space;=&space;-\log(D(G(z))))

Where:
- **D(G(z))** is the discriminator's output when evaluating the generator's output, given random noise **z** as input.


**Discriminator Loss (L<sub>D</sub>)**

The discriminator's role is to differentiate between real and generated samples. Its loss is composed of two terms: one corresponding to the classification error for real samples and the other for fake samples. The discriminator aims to maximize its accuracy in distinguishing real from fake samples.

![Discriminator Loss](https://latex.codecogs.com/svg.image?L_D&space;=&space;-\log(D(x))&space;-&space;\log(1&space;-&space;D(G(z))))

Where:
- **D(x)** is the discriminator's output when evaluating a real data sample **x**.
- **D(G(z))** is the discriminator's output when evaluating the generator's output, given random noise **z** as input.

 > #### L = log(sigmoid(D(x))) + log(1-sigmoid(D(G(z))))

These loss functions create an adversarial training process, where the generator aims to minimize its loss by generating samples that the discriminator considers real, while the discriminator aims to maximize its loss by correctly classifying real and generated samples.

### Nash Equilibrium

GAN is based on the zero-sum non-cooperative game. In short, if one wins the other loses. A zero-sum game is also called minimax. Your opponent wants to maximize its actions and your actions are to minimize them. In game theory, the GAN model converges when the discriminator and the generator reach a Nash equilibrium. This is the optimal point for the minimax equation below.

![nash1](https://miro.medium.com/v2/resize:fit:828/format:webp/1*l9se1koH_eQdZesko5eQpw.jpeg)

The Nash equilibrium refers to a scenario in which there exists no motivation for players to stray from their initial strategy alone. Consider two player A and B which control the value of x and y respectively. Player A wants to maximize the value xy while B wants to minimize it.

![nash2](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*5FT0yTKZhl1JsxR6uN026w.jpeg)

The Nash equilibrium is x=y=0. This is the state where the change of mind of a single player will not improve the result. 



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



## TSNE








---

---

<h2 align="center">Behind this Work</h2>

<div style="display: flex; justify-content: space-between; align-items: center;">
  
  <div align="center">
    <img src="https://scontent.fccu2-1.fna.fbcdn.net/v/t39.30808-6/393301579_742609554547890_7961942992814070818_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=5f2048&_nc_ohc=fvfTdJJ1_iAAX-3fEZ8&_nc_ht=scontent.fccu2-1.fna&oh=00_AfAokw2OVevzWc0xwnm3I_3TbFCxFQiVYkRm0CRNvbr2mQ&oe=65698094" height="200" alt="Ritwik" width="175">
    <p><b>Ritwik Ganguly</b></p>
    <p align="center">
    <a href="https://www.linkedin.com/in/ritwikganguly003/" target="blank"><img align="center" src="https://www.svgrepo.com/show/110195/linkedin.svg" alt="ritwik-ganguly-148aa2203" height="30" width="40" /></a>
    <a href="https://medium.com/@gangulyritwik2003" target="blank"><img align="center" src="https://www.svgrepo.com/show/354057/medium-icon.svg" alt="ritwik-ganguly-148aa2203" height="30" width="40" /></a>
    <a href="https://github.com/RitwikGanguly" target="blank"><img align="center" src="https://www.svgrepo.com/show/512317/github-142.svg" alt="ritwik" height="30" width="40" /></a>
    </p>
  </div>
  <div align="center">
    <img src="https://scontent.fccu2-2.fna.fbcdn.net/v/t39.30808-6/399241950_843557810824379_7883884432871232091_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=5f2048&_nc_ohc=6yTOdzf89xUAX9aOr1e&_nc_ht=scontent.fccu2-2.fna&oh=00_AfB3hLNzxCXBbGtlO3VB43sTaC-XSglFUjXe73NnlwUvyA&oe=65691322" height="200" alt="Nilanjana" width="185">
    <p><b>Nilanjana Bhattacharya</b></p>
    <p align="center">
    <a href="https://www.linkedin.com/in/nilanjana-bhattacharya-270007263/" target="blank"><img align="center" src="https://www.svgrepo.com/show/110195/linkedin.svg" alt="ritwik-ganguly-148aa2203" height="30" width="40" /></a>
    <a href="https://medium.com/@gangulyritwik2003" target="blank"><img align="center" src="https://www.svgrepo.com/show/354057/medium-icon.svg" alt="ritwik-ganguly-148aa2203" height="30" width="40" /></a>
    <a href="https://github.com/RitwikGanguly" target="blank"><img align="center" src="https://www.svgrepo.com/show/512317/github-142.svg" alt="ritwik" height="30" width="40" /></a>
    </p>
  </div>
  
  <div align="center">
    <img src="https://media.licdn.com/dms/image/D4D03AQEaz1a6yN2fmw/profile-displayphoto-shrink_800_800/0/1679486077155?e=1701302400&v=beta&t=Ns7pru7F3j4GicZewd3upyHQ_mUzHUhskMLioaxOYV4" height="200" alt="Sruti" width="200">
    <p><b>Sruti de</b></p>
    <p align="center">
    <a href="https://www.linkedin.com/in/ritwikganguly003/" target="blank"><img align="center" src="https://www.svgrepo.com/show/110195/linkedin.svg" alt="ritwik-ganguly-148aa2203" height="30" width="40" /></a>
    <a href="https://medium.com/@gangulyritwik2003" target="blank"><img align="center" src="https://www.svgrepo.com/show/354057/medium-icon.svg" alt="ritwik-ganguly-148aa2203" height="30" width="40" /></a>
    <a href="https://github.com/RitwikGanguly" target="blank"><img align="center" src="https://www.svgrepo.com/show/512317/github-142.svg" alt="ritwik" height="30" width="40" /></a>
    </p>
  </div>
  
</div>
