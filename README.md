# Spotify Track Genre Classification

> Top 6 Winner – Data Sprint 2026 Machine Learning Hackathon
>
> Organized by NIST University in collaboration with HackerRank
>
> Ranked among the Top 6 teams out of 3000+ participants across India.

---

## Overview

This project tackles a large-scale multiclass classification problem:

**Predict the genre of a Spotify track from its audio characteristics and metadata.**

The dataset contains information such as:

- Danceability
- Energy
- Loudness
- Speechiness
- Acousticness
- Instrumentalness
- Tempo
- Popularity
- Artist metadata
- Album metadata
- Track metadata

The challenge involves classifying tracks into **114 different music genres**, making it a high-dimensional multiclass machine learning problem.

---

## Competition Achievement

🏆 Top 6 Winner

- 3000+ participants
- National-level Machine Learning Hackathon
- Organized by NIST University
- Supported by HackerRank
- Prize Pool: ₹1.2 Lakhs

---

## Problem Statement

Given Spotify track metadata and audio features, predict the corresponding music genre.

This is a:

- Multiclass Classification Problem
- 114 Genre Classes
- Tabular + Text Feature Learning Task

---

## Project Pipeline

### 1. Data Cleaning

Performed preprocessing to ensure consistency across train and test data:

- Removed unnecessary columns
- Fixed datatype inconsistencies
- Handled missing values
- Standardized categorical variables
- Cleaned metadata fields

---

### 2. Exploratory Data Analysis

Investigated:

- Genre distribution
- Audio feature distributions
- Feature correlations
- Genre-specific audio signatures
- Explicit content patterns
- Genre similarity structure

Key findings:

- Dataset was relatively balanced
- Strong correlation between energy and loudness
- Distinct genre clusters emerged from audio features
- Certain genres exhibited highly overlapping feature spaces

---

### 3. Feature Engineering

Feature engineering was the most important part of the solution.

#### Text Features

Applied TF-IDF vectorization on:

- Track names
- Album names

This allowed the model to capture genre-related textual signals.

Examples:

- Classical compositions
- Metal tracks
- EDM naming patterns

---

#### Artist Encoding

Implemented artist-based target encoding.

Rationale:

Artists often have strong genre consistency, making artist identity a highly informative feature.

---

#### Interaction Features

Generated domain-inspired features including:

- Energy × Loudness
- Acousticness × Instrumentalness
- Popularity-based interactions
- Rhythm-related combinations

These features improved separability between closely related genres.

---

### 4. Feature Selection

Used LightGBM feature importance scores to identify and retain the most informative features.

Benefits:

- Reduced noise
- Improved generalization
- Lower computational cost

---

### 5. Model Development

Several models were evaluated using stratified cross-validation.

Models tested:

- LightGBM
- XGBoost
- Random Forest

Evaluation metrics:

- Accuracy
- Macro F1 Score
- Cross-validation consistency

---

### 6. Error Analysis

Performed extensive post-training analysis:

- Classification reports
- Per-genre F1 scores
- Confusion matrix analysis
- Hardest genre pair identification

Common failure cases included:

- Rock vs Alternative Rock
- Related electronic subgenres
- Closely overlapping audio profiles

---

## Tech Stack

### Languages

- Python

### Libraries

- Pandas
- NumPy
- Scikit-learn
- LightGBM
- XGBoost
- Matplotlib
- Seaborn
- Joblib

---

## Repository Structure

```text
.
├── notebook.ipynb
├── train.csv
├── test.csv
├── submission.csv
├── best_model.pkl
└── README.md