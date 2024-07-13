# Protein-Ligand Binding Affinity Prediction

## Overview

Structure-based drug design (SBDD) is a powerful approach for identifying drug candidates by evaluating docking poses and estimating the interaction strength between target proteins and small molecules (ligands). Strong interactions indicate potential drug candidates that can influence the physiological functions of target proteins. 

This project leverages advanced machine learning techniques to accurately predict protein-ligand binding affinities. By integrating Deep Kernel Learning and transfer learning from the pre-trained model `protein-ligand-mlp-3` by Jens Glaser, we aim to significantly reduce the cost and time associated with developing new drugs. Our model's predictive capabilities offer a promising solution to accelerate drug discovery, particularly crucial in the context of emerging infectious diseases like COVID-19.

## Objectives

- Predict the binding affinity between proteins and ligands based on structural data.
- Apply deep learning and deep kernel learning techniques to improve prediction accuracy.

## Methods

### Deep Learning

Deep learning is a subset of artificial intelligence (AI) and machine learning that focuses on creating and training artificial neural networks to perform tasks similar to how the human brain processes and learns information.

![Deep Learning Model Architecture](URL-of-deep-learning-image)

### Deep Kernel Learning

Deep kernel learning combines the strengths of deep learning and kernel methods. It uses neural networks to learn hierarchical representations of data while leveraging kernel functions to handle nonlinear patterns.

![Deep Kernel Learning Model Architecture](URL-of-deep-kernel-learning-image)

## Experimental Results

### Dataset

#### Source

- Protein-ligand complexes (The refined set): Data package of the refined set, including index files summarizing the basic information and processed structural files for the protein-ligand complexes included in this data set (proteins saved in PDB format; ligands saved in Mol2 and SDF format). This data package includes 5316 complexes in total.
- We can download [here](http://www.pdbbind.org.cn/download.php).

#### Preprocessing

To parse protein sequences and ligand sequences, we use cheminformatics packages such as Bio and RDKit.

We tested our models on a dataset of protein-ligand complexes and obtained promising results, demonstrating the potential of these methods in predicting binding affinities.

### Deep Learning

This is the evaluation result of the model on the test set:

| Metrics                          | Test   |
|----------------------------------|--------|
| Mean Squared Error               | 1.036  |
| Root Mean Squared Error          | 1.018  |
| Mean Absolute Error              | 0.692  |
| Mean Absolute Percentage Error   | 0.117  |
| Spearman's Rho                   | 0.866  |
| R-Squared                        | 0.723  |

### Deep Kernel Learning

This is the evaluation result of the model on the test set:

| Metrics                          | Test   |
|----------------------------------|--------|
| Mean Squared Error               | 0.982  |
| Root Mean Squared Error          | 0.991  |
| Mean Absolute Error              | 0.711  |
| Mean Absolute Percentage Error   | 0.128  |
| Spearman's Rho                   | 0.871  |
| R-Squared                        | 0.746  |

## References
* A. E Blanchard, J. Gounley, D. Bhowmik, M. C. Shekar, I. Lyngaas, S. Gao, J. Yin, A. Tsaris, F. Wang and J. Glaser, "Language Models for the Prediction of SARS-CoV-2 Inhibitors", published in The International Journal of High Performance Computing Applications, 2021
* S. Seo, J. Choi, S. Park and J. Ahn, "Binding affinity prediction for protein–ligand complex using deep attention mechanism based on intermolecular interactions", BMC Bioinformatics 22, 2021.
* A. G. Wilson, Z. Hu, R. Salakhutdinov, E. P. Xing, Deep Kernel Learning, Artificial intelligence and statistics, 2016
* GPyTorch, Exact DKL (Deep Kernel Learning) Regression w/ KISS-GP
