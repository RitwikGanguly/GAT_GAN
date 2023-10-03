# GAT GAN

---

# Index of the Document
| Topics in Project | 
|--|
| 1. [Description of the Project](#Project-Description) | 
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

---

<h2 align="center">Behind this Work</h2>

<div style="display: flex; justify-content: space-between; align-items: center;">
  
  <div align="center">
    <img src="https://scontent.fccu11-1.fna.fbcdn.net/v/t39.30808-6/385863541_731240315684814_9041053619138049891_n.jpg?_nc_cat=109&ccb=1-7&_nc_sid=49d041&_nc_ohc=cjPDyQTPaYkAX_kAJQI&_nc_ht=scontent.fccu11-1.fna&oh=00_AfCLTSNS_83uunO58mpR6rMqNwwRXv_g6kngXtEsfGeUfw&oe=6520163F" height="200" alt="Developer 1" width="200">
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
