# Investigating the Effect of Edge-Weighting Strategies on Community Detection in Book Networks

### Using the Goodbooks-10k Dataset

## About the Project

This research investigates how different edge-weighting strategies affect community detection in book networks using the Goodbooks-10k dataset.

Three approaches are compared:
- **Unweighted:** All edges have equal weight.
- **Shared-Tag-Count:** Edge weights represent the number of shared tags.
- **Jaccard Similarity:** Edge weights represent the proportion of shared tags between two books.

The Louvain algorithm is used for community detection, with modularity, seed stability and Adjusted Rand Index (ARI) used for evaluation.

## Research Objectives

- Construct a book network using shared tags.
- Compare three edge-weighting strategies.
- Apply Louvain community detection.
- Evaluate modularity and community stability.
- Compare community assignments using ARI.
- Explore supporting machine learning and linear programming approaches.

## Dataset

**Goodbooks-10k Dataset**

Source: [Kaggle – Goodbooks-10k](https://www.kaggle.com/datasets/zygmunt/goodbooks-10k)

The dataset contains book information, user ratings, tags and reading preferences.

## Methodology

1. Data collection and preprocessing.
2. Book network construction.
3. Edge-weight calculation using three strategies.
4. Louvain community detection.
5. Modularity and stability evaluation.
6. ARI comparison.
7. Supporting machine learning and linear programming experiments.

## Main Results

| Edge-Weighting Strategy | Modularity | Communities |
|---|---:|---:|
| Unweighted | 0.34795 | 6 |
| Shared-Tag-Count | 0.59679 | 8 |
| Jaccard | **0.61875** | 8 |

### Random Seed Stability

Mean modularity across five random seeds:

| Strategy | Mean Modularity |
|---|---:|
| Unweighted | 0.34684 |
| Shared-Tag-Count | 0.59893 |
| Jaccard | **0.62054** |

Jaccard achieved the highest average modularity across the five tested seeds.

### ARI Comparison

Shared-Tag-Count and Jaccard produced the highest agreement, with a mean ARI of **0.84245**.

## Supporting Experiments

**Machine Learning**
- Logistic Regression
- Linear SVM
- Random Forest
- Histogram Gradient Boosting

**Linear Programming**
- Book selection using relevance and community diversity.
- Comparison with a relevance-based Top-K baseline.

## Technologies Used

- Python
- Pandas & NumPy
- NetworkX
- Scikit-learn
- Matplotlib & Seaborn
- SciPy
- Jupyter Notebook

## Project Structure

```text
goodbooks10k-edge-weighted-community-detection/
│
├── data/
│   └── processed/
│
├── notebooks/
│   ├── 01_data_preparation.ipynb
│   ├── 02_graph_construction_and_communities.ipynb
│   ├── 03_ML_Book_Rating_Prediction.ipynb
│   └── 04_Linear_Programming_Book_Recommendation.ipynb
│
├── outputs/
│   ├── figures/
│   └── tables/
│
├── README.md
├── requirements.txt
└── .gitignore
```

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/goodbooks10k-edge-weighted-community-detection.git
```

Navigate to the project:

```bash
cd goodbooks10k-edge-weighted-community-detection
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Open Jupyter Notebook:

```bash
jupyter notebook
```

## Limitations

- The main graph experiment uses a selected subset of 2,000 books.
- Results depend on tag filtering and network construction settings.
- Machine learning results are exploratory and do not represent a personalised recommendation system.
- The linear programming experiment uses book-level relevance proxies rather than individual user preferences.

## Acknowledgements

The Goodbooks-10k dataset was used as the primary data source for this research.

**Note:** This project is an undergraduate academic research study.
