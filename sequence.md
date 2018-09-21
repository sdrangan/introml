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
    * [Lab: Student performance prediction](./unit05_lasso/lab_student-performance.ipynb) 
    * Problems [[pdf]](./unit05_lasso/prob/prob_lasso.pdf) [[Latex]](./unit05_lasso/prob/prob_lasso.tex)
* [Unit 6:  Logistic regression](./unit04_logistic/readme.md)
    * Lecture:  Linear classification and logistic regression
    [[pdf]](./lectures/Lect06_LogisticReg.pdf)
    [[Powerpoint]](./lectures/Lect06_LogisticReg.pptx)         
    * [Demo:  Breast cancer diagnosis via logistic regression](./unit04_logistic/demo04_breast_cancer.ipynb)
    * [Lab: Genetic analysis of Down's syndrome in mice](./unit04_logistic/lab04_gene_partial.ipynb)
    * Problems [[pdf]](./unit04_logistic/hw/hw04_logistic.pdf)
    [[Latex]](./unit04_logistic/hw/hw04_logistic.tex) 
* [Unit 7:  Nonlinear optimization](./unit05_optim/readme.md)
    * Lecture:  Nonlinear optimization and gradient descent
    [[pdf]](./lectures/Lect07_Optim.pdf)
    [[Powerpoint]](./lectures/Lect07_Optim.pptx)         
    * [Demo 1:  Computing gradients](./unit05_optim/demo05_1_computing_gradients.ipynb)
    * [Demo 2:  Simple gradient descent optimization](./unit05_optim/demo05_2_grad_descent.ipynb)    
    * [Lab: Audio pitch detection](./unit05_optim/lab05_audio_partial.ipynb)
    * Problems [[pdf]](./unit05_optim/hw/hw05_optim.pdf)
    [[Latex]](./unit05_optim/hw/hw05_optim.tex)
* [Unit 8:  Support vector machines](./unit06_svm/readme.md)
    * Lecture:  SVM [[pdf]](./lectures/Lect08_SVM.pdf)
    [[Powerpoint]](./lectures/Lect08_SVM.pptx)         
    * [Demo:  MNIST digit classification](./unit06_svm/demo06_mnist_svm.ipynb)
    * [Lab: Extended MNIST with letters](./unit06_svm/lab06_emnist_partial.ipynb)    
    * Problems [[pdf]](./unit06_svm/hw/hw06_svm.pdf) [[Latex]](./unit06_svm/hw/hw06_svm.tex) 
* Unit 9: Statistical Learning Theory
    * To be developed
* [Unit 10: Neural networks with Keras and Tensorflow](./unit07_neural/readme.md)
    * Lecture:  Neural networks [[pdf]](./lectures/Lect09_NeuralNet.pdf)
    [[Powerpoint]](./lectures/Lect09_NeuralNet.pptx)         
    * Supplementary notes with solved problems [[pdf]](./unit07_neural/hw/supplementary_neural.pdf) [[Latex]](./unit07_neural/hw/supplementary_neural.tex)
    * [Demo 1: First neural network in Keras](./unit07_neural/demo07_1_synthetic.ipynb)
    * [Demo 2: MNIST neural network classification](./unit07_neural/demo07_2_mnist_neural.ipynb)
    * [Lab:  Music instrument classification](./unit07_neural/lab07_music_partial.ipynb)
    * [In-class Exercise](./unit07_neural/InclassExercise.ipynb)
    * Problems: [[pdf]](./unit07_neural/hw/hw07_neural.pdf) [[Latex]](./unit07_neural/hw/hw07_neural.tex)    
* [Unit 11:  Convolutional and deep networks](./unit08_cnn/readme.md)
    * Lecture:  Convolutional and deep networks
    [[pdf]](./lectures/Lect10_ConvNet.pdf)
    [[Powerpoint]](./lectures/Lect10_ConvNet.pptx)         
    * [Setting up a GPU instance](./GCP/gpu_setup.md) (Recommended)
    * [Demo 1: 2D convolutions and convolutional layers in keras](./unit08_cnn/demo08_1_convolutions.ipynb)
    * [Demo 2: Creating an image set using the Flickr API](./unit08_cnn/demo08_2_flickr_images.ipynb)
    * [Demo 3: Exploring the deep VGG16 network](./unit08_cnn/demo08_3_vgg16.ipynb)
    * [Demo 4: Building an image classifier using CIFAR10 dataset](./unit08_cnn/demo08_4_classifier.ipynb)
    * [Demo 5: Building an autoencoder for image denoising using CIFAR10 dataset](./unit08_cnn/demo08_5_autoencoder.ipynb)
    * [Lab:  Transfer learning with a pre-trained network](./unit08_cnn/lab08_fine_tune_partial.ipynb)
    (GPU recommended)
    * Problems [[pdf]](./unit08_cnn/hw/hw08_cnn.pdf) [[Latex]](./unit08_cnn/hw/hw08_cnn.tex)
* [Unit 12:  PCA](./pca/readme.md)
    * Lecture:  PCA [[pdf]](./lectures/Lect11_PCA.pdf), Modifed Note [[pdf]](./lectures/Lect11_PCA_modified.pdf)
    [[Powerpoint]](./lectures/Lect11_PCA_modified.pptx)         
    * [Demo:  PCA eigen-faces-SVM](./unit09_pca/demo09_eigen_face_SVM.ipynb)
    * [Lab 1:  PCA with NN vs CNN](./unit09_pca/Lab09a_pca_NN_CNN_partial.ipynb)
    * [Lab 2: Movie recommendations](./unit09_pca/lab09_movies_partial.ipynb) (Not required) 
    * Problems [[pdf]](./unit09_pca/hw/hw09_PCA.pdf) [[Latex]](./unit09_pca/hw/hw09_PCA.tex)
* [Unit 13:  Clustering and EM](./unit10_cluster/readme.md)
    * Lecture:  Clustering and EM [[pdf]](./lectures/Lect12_Clustering.pdf)
    [[Powerpoint]](./lectures/Lect12_Clustering.pptx)         
    * [Demo 1: Document clustering via k-means and latent semantic analysis](./unit10_cluster/demo10_doc_cluster.ipynb)
    * [Demo 2: Color quantization via k-means and EM-GMM](./unit10_cluster/demo10b_kmeans_GMM_color_quantization.ipynb)    
    * Homework [[pdf]](./unit10_cluster/hw/hw10_clustering.pdf) [[Latex]](./unit10_cluster/hw/hw10_clustering.tex)
* Unit 14:  Decision Trees and Random Forest
    * Lecture:  Decision tree and random foreast [[pdf]](./lectures/Lect13_Trees.pdf)
    [[Powerpoint]](./lectures/Lect13_Trees.pptx)         
    * [Demo: Prediction of temperature using decision tree and random forest](./unit11_tree/decision_tree_and_random_forest.ipynb)
    * Homework [[pdf]](./unit11_tree/hw/hw11_tree.pdf) [[Latex]](./unit11_tree/hw/hw11_tree.tex)

