[Return to home page](./README.md) 

# Table of Contents

The course is taught in a sequence of units.  Each unit takes between one
and two weeks so that the entire class can be fit into a single semester.
Most units currently have four components:
* **Lecture Notes**:  These are slides accompanying the class lecture.  They include code snippets
   from the demos.   
* **Demo**: These are python-based [Jupyter notebooks](http://jupyter.org/)
   for demonstrations given during the lectures.  Some demos have a
   component that is done in class.  The demos do not generally cover
   all topics, since some concepts are left for the students to figure out 
   for themselves in the labs.
* **Lab**:  Following the lecture, the students do a python-based exercise at home
   that builds on the demo.
   The labs in the repository are given as skeletons with `TODO`
   markers that the students fill in.
* **Problems**:  These are more analytic problems, also done at home.

The problem and lab solutions are provided to students enrolled in the class.
If you are an instructor
and wish copies of the solutions for yourself,
please contact Sundeep Rangan at <srangan@nyu.edu>.

This site is undergoing re-numbering of units, so many links may connect
to documents that don't match the number of the unit.  We will fix these soon!

* [Setting up python, jupyter and github](./Basics/setup.md)
    * [Set up a local machine](./Basics/setup.md)
    * [Set up a virtual machine in Google Cloud Platform](./GCP/getting_started.md)
    * [Set up a virtual machine in Google Cloud Platform with Docker](./GCP/docker.md)
    * [Downloading the course material from github](./Basics/github.md)
    * [Set up a GPU machine](./GCP/gpu_setup.md)  (Needed for Unit 10)
* Introduction
    * Course Admin [[pdf]](./lectures/CourseAdmin.pdf) [[Powerpoint]](./lectures/CourseAdmin.pptx)
* Unit 1:  What is machine learning? 
    * Lecture:  Introduction to Machine Learning [[pdf]](./lectures/Lect01_IntroML.pdf)
     [[Powerpoint]](./lectures/Lect01_IntroML.pptx)    
     * [Demo:  Introduction to numpy vectors](./unit01_intro/demo_intro_vectors.ipynb)
* Unit 2:  Simple linear regression
    * Lecture:  Simple linear regression [[pdf]](./lectures/Lect02_SimpRegression.pdf)
     [[Powerpoint]](./lectures/Lect02_SimpRegression.pptx)        
    * [Demo:  Understanding automobile mpg](./unit02_simp_lin_reg/demo2_auto_mpg.ipynb)
    * [Lab: Boston housing data](./unit02_simp_lin_reg/lab_housing_partial.ipynb) 
    * Problems [[pdf]](./unit02_simp_lin_reg/prob/prob_simp_lin_reg.pdf) [[Latex]](./unit02_simp_lin_reg/prob/prob_simp_lin_reg.tex)
* Unit 3:  Multiple linear regression
    * Lecture:  Multiple linear regression [[pdf]](./lectures/Lect03_MultLinRegression.pdf)
     [[Powerpoint]](./lectures/Lect03_MultLinRegression.pptx)    
    * [Demo 1:  Predicting glucose levels](./unit03_mult_lin_reg/demo1_glucose.ipynb)
    * [Demo 2:  Python broadcasting](./unit03_mult_lin_reg/demo2_python_broadcasting.ipynb)
    * [Lab: Calibrating robot dynamics](./unit03_mult_lin_reg/lab_robot_calib_partial.ipynb)
    * Problems [[pdf]](./unit03_mult_lin_reg/prob/prob_mult_reg.pdf) [[Latex]](./unit03_mult_lin_reg/prob/prob_mult_reg.tex)
* Unit 4:  Model selection
    * Lecture:  Model selection [[pdf]](./lectures/Lect04_ModelSelection.pdf)
     [[Powerpoint]](./lectures/Lect04_ModelSelection.pptx)    
    * [Demo:  Polynomial order selection with cross-validation](./unit04_model_sel/demo_polyfit.ipynb)
    * [Lab: Neural decoding motor cortex signals](./unit04_model_sel/lab_neural_partial.ipynb)          
    * Problems [[pdf]](./unit04_model_sel/prob/prob_model_sel.pdf) [[Latex]](./unit03_model_sel/hw/hw03_model_sel.tex)    
* Unit 5:  Regularization and LASSO
    * Lecture:  LASSO Regularization [[pdf]](./lectures/Lect05_Lasso.pdf)
     [[Powerpoint]](./lectures/Lect05_Lasso.pptx)         
    * [Demo:  Finding predictors of prostate cancer](./unit05_lasso/demo_prostate.ipynb) 
    * [Lab: EEG source localization](./unit05_lasso/lab_eeg_partial.ipynb) 
    * Problems [[pdf]](./unit05_lasso/prob/prob_lasso.pdf) [[Latex]](./unit05_lasso/prob/prob_lasso.tex)
* [Unit 6:  Logistic regression](./unit06_logistic/readme.md)
    * Lecture:  Linear classification and logistic regression
    [[pdf]](./lectures/Lect06_LogisticReg.pdf)
    [[Powerpoint]](./lectures/Lect06_LogisticReg.pptx)         
    * [Demo:  Breast cancer diagnosis via logistic regression](./unit06_logistic/demo_breast_cancer.ipynb)
    * [Lab: Genetic analysis of Down's syndrome in mice](./unit06_logistic/lab_gene_partial.ipynb)
    * Problems [[pdf]](./unit06_logistic/prob/prob_logistic.pdf)
    [[Latex]](./unit06_logistic/prob/prob_logistic.tex) 
* [Unit 7:  Nonlinear optimization](./unit07_optim/readme.md)
    * Lecture:  Nonlinear optimization and gradient descent
    [[pdf]](./lectures/Lect07_Optim.pdf)
    [[Powerpoint]](./lectures/Lect07_Optim.pptx)         
    * [Demo 1:  Computing gradients](./unit07_optim/demo1_computing_gradients.ipynb)
    * [Demo 2:  Simple gradient descent optimization](./unit07_optim/demo2_grad_descent.ipynb)    
    * [Lab: Nonlinear least squares material modeling](./unit07_optim/lab_nlls_partial.ipynb)
    * Problems [[pdf]](./unit07_optim/prob/prob_optim.pdf)
    [[Latex]](./unit07_optim/prob/prob_optim.tex)
* [Unit 8:  Support vector machines](./unit08_svm/readme.md)
    * Lecture:  SVM [[pdf]](./lectures/Lect08_SVM.pdf)
    [[Powerpoint]](./lectures/Lect08_SVM.pptx)         
    * [Demo:  MNIST digit classification](./unit08_svm/demo_mnist_svm.ipynb)
    * [Lab: Extended MNIST with letters](./unit08_svm/lab_emnist_partial.ipynb)    
    * Problems [[pdf]](./unit08_svm/prob/prob_svm.pdf) [[Latex]](./unit08_svm/prob/prob_svm.tex) 
* [Unit 9: Neural networks with Keras and Tensorflow](./unit09_neural/readme.md)
    * Lecture:  Neural networks [[pdf]](./lectures/Lect09_NeuralNet.pdf)
    [[Powerpoint]](./lectures/Lect09_NeuralNet.pptx)         
    * Supplementary notes with solved problems [[pdf]](./unit09_neural/prob/supplementary_neural.pdf) [[Latex]](./unit09_neural/prob/supplementary_neural.tex)
    * [Demo 1: First neural network in Keras](./unit09_neural/demo1_synthetic.ipynb)
    * [Demo 2: MNIST neural network classification](./unit09_neural/demo2_mnist_neural.ipynb)
    * [Lab:  Music instrument classification](./unit09_neural/lab_music_partial.ipynb)
    * [In-class Exercise](./unit09_neural/in_class_exercise.ipynb)
    * Problems: [[pdf]](./unit09_neural/prob/prob_neural.pdf) [[Latex]](./unit97_neural/prob/prob_neural.tex)    
* [Unit 10:  Convolutional and deep networks](./unit10_cnn/readme.md)
    * Lecture:  Convolutional and deep networks
    [[pdf]](./lectures/Lect10_ConvNet.pdf)
    [[Powerpoint]](./lectures/Lect10_ConvNet.pptx)         
    * [Setting up a GPU instance](./GCP/gpu_setup.md) (Recommended)
    * [Demo 1: 2D convolutions and convolutional layers in keras](./unit10_cnn/demo1_convolutions.ipynb)
    * [Demo 2: Creating an image set using the Flickr API](./unit10_cnn/demo2_flickr_images.ipynb)
    * [Demo 3: Exploring the deep VGG16 network](./unit10_cnn/demo3_vgg16.ipynb)
    * [Demo 4: Building an image classifier using CIFAR10 dataset](./unit10_cnn/demo4_classifier.ipynb)
    * [Demo 5: Building an autoencoder for image denoising using CIFAR10 dataset](./unit10_cnn/demo5_autoencoder.ipynb)
    * [Lab:  Transfer learning with a pre-trained network](./unit10_cnn/lab_fine_tune_partial.ipynb)
    (GPU recommended)
    * Problems [[pdf]](./unit10_cnn/prob/prob_cnn.pdf) [[Latex]](./unit10_cnn/prob/prob_cnn.tex)
* [Unit 11:  PCA](./pca/readme.md)
    * Lecture:  PCA [[pdf]](./lectures/Lect11_PCA.pdf), Modifed Note [[pdf]](./lectures/Lect11_PCA_modified.pdf)
    [[Powerpoint]](./lectures/Lect11_PCA_modified.pptx)         
    * [Demo:  PCA eigen-faces-SVM](./unit11_pca/demo1_eigen_face_SVM.ipynb)
    * [Lab 1:  PCA with NN vs CNN](./unit11_pca/lab_pca_nn_cnn_partial.ipynb)
    * [Lab 2: Movie recommendations](./unit11_pca/lab_movies_partial.ipynb) (Not required) 
    * Problems [[pdf]](./unit11_pca/prob/prob_PCA.pdf) [[Latex]](./unit11_pca/prob/prob_PCA.tex)
* [Unit 12:  Clustering and EM](./unit12_cluster/readme.md)
    * Lecture:  Clustering and EM [[pdf]](./lectures/Lect12_Clustering.pdf)
    [[Powerpoint]](./lectures/Lect12_Clustering.pptx)         
    * [Demo 1: Document clustering via k-means and latent semantic analysis](./unit12_cluster/demo1_doc_cluster.ipynb)
    * [Demo 2: Color quantization via k-means and EM-GMM](./unit12_cluster/demo2_kmeans_GMM_color_quantization.ipynb)    
    * Homework [[pdf]](./unit12_cluster/prob/prob_clustering.pdf) [[Latex]](./unit12_cluster/prob/prob_clustering.tex)
* Unit 13:  Decision Trees and Random Forest
    * Lecture:  Decision tree and random foreast [[pdf]](./lectures/Lect13_Trees.pdf)
    [[Powerpoint]](./lectures/Lect13_Trees.pptx)         
    * [Demo: Prediction of temperature using decision tree and random forest](./unit13_tree/decision_tree_and_random_forest.ipynb)
    * Homework [[pdf]](./unit13_tree/prob/prob_tree.pdf) [[Latex]](./unit13_tree/prob/prob_tree.tex)

