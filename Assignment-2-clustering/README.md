# Text Clustering of Computer Science Research Abstracts

## Overview

This project explores unsupervised clustering of approximately 1,000 research paper abstracts from five computer science subfields:

-   Computer Vision
-   Machine Learning
-   Natural Language Processing
-   Robotics
-   Cryptography / Security

The objective is to compare different document representations and clustering algorithms to understand how scientific research domains organize semantically.

The project evaluates:

-   Classical lexical representations (TF-IDF)
-   Topic-based representations (LDA)
-   Semantic embeddings (SBERT)

and compares clustering approaches including:

-   K-Means
-   Gaussian Mixture Models (EM)
-   Hierarchical Agglomerative Clustering

Evaluation metrics include Cohen's Kappa (label alignment) and Silhouette Score (geometric separation).

------------------------------------------------------------------------

## Setup Instructions

### 1. Create a virtual environment

**Windows:**

python -m venv .venv ..venv`\Scripts`{=tex}`\activate`{=tex}

**Mac/Linux:**

python3 -m venv .venv source .venv/bin/activate

### 2. Install dependencies

pip install -r requirements.txt

------------------------------------------------------------------------

## Running the Project

### Step 1 --- Data Preparation

Run:

notebooks/clustering_assignment_2.ipynb

This notebook:

-   prepares the dataset
-   standardizes text (\~150-word records)
-   creates stratified splits
-   performs preprocessing

### Step 2 --- Feature Engineering & Clustering

Run:

notebooks/features_clustering.ipynb

This notebook:

-   generates TF-IDF, LDA, and SBERT features
-   runs clustering algorithms
-   saves cluster assignments
-   produces evaluation metrics and visualizations

Running all cells regenerates:

-   feature matrices
-   clustering outputs
-   evaluation results
-   diagnostic plots

------------------------------------------------------------------------

## Reproducibility Notes

To ensure consistent results:

-   Random seed fixed at 42 across experiments
-   Stratified train/validation/test splits used
-   Feature matrices and clustering outputs saved to disk
-   Evaluation metrics stored in outputs/evaluation_results.csv

------------------------------------------------------------------------

## Key Findings (Summary)

-   SBERT embeddings with Gaussian Mixture Models provided the strongest alignment with known research categories.
-   LDA topic representations produced clearer geometric separation but weaker alignment with labels.
-   Misclusterings largely reflect interdisciplinary overlap rather than algorithmic error.
-   Cryptography/security papers form the most distinct cluster; machine learning overlaps with multiple domains.

------------------------------------------------------------------------

## Requirements

Main dependencies:

-   Python ≥ 3.9
-   pandas
-   numpy
-   scikit-learn
-   scipy
-   matplotlib
-   sentence-transformers
-   nltk
-   umap-learn

Exact versions are listed in requirements.txt.

------------------------------------------------------------------------

## Notes for Course Submission

This repository intentionally excludes:

-   virtual environments (.venv/)
-   cache files (**pycache**/, .ipynb_checkpoints/)
-   temporary or log files

Only necessary code, data, and documentation are included.

------------------------------------------------------------------------