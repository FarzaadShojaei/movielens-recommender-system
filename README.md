# MovieLens Recommender System

Comparing collaborative filtering and neural approaches for movie recommendation on the MovieLens 1M dataset.

## What's in here

We implemented and evaluated 5 models, starting from the simplest possible baseline and working up to a neural architecture:

| Model | Type |
|---|---|
| Popularity Baseline | Non-personalized |
| User-Based CF | Memory-based |
| Item-Based CF | Memory-based |
| SVD (Matrix Factorization) | Representation learning |
| NeuMF + Warm-Start NeuMF | Neural Collaborative Filtering |

## Dataset

[MovieLens 1M](https://grouplens.org/datasets/movielens/1m/) — 1M ratings from 6,040 users across ~3,900 movies. Ratings ≥ 4 stars are treated as positive interactions (implicit feedback).

## Evaluation

All models are evaluated using a **Leave-One-Out / 1-vs-99 protocol** — each user's last interaction is held out as the test item and ranked against 99 randomly sampled negatives.

**Metrics:** Precision@10, Recall@10, NDCG@10

## Results

NeuMF outperformed all baselines across every metric, especially NDCG@10 — meaning it not only finds the right movie more often, it ranks it higher in the list.

## How to run

Open the notebook in Google Colab. When prompted, you can either load the pretrained model weights or train from scratch (training takes ~1–1.5 hours on a GPU).

## Stack

`Python` `PyTorch` `scikit-learn` `pandas` `numpy` `matplotlib`

## Team

| Name | Role |
|---|---|
| Farzad Shojaei | Problem Definition, Baselines, Evaluation, Discussion |
| Melina Mokhtari | Data Exploration & Preprocessing |
| Sogol Shishechiha | Item-Based CF |
| Saeed Sabzeh | NeuMF Architecture & Training |
| Emanuele Iaconis | Evaluation Methodology & Reproducibility |
