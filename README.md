# Beyond the Prompt: A Quantitative Study of ChatGPT vs. DeepSeek
**Authors**: Matthew Fredrik, Akhil Krishnan, Sanjay Mohan Kumar, Stefan Popescu  

## Introduction  

### Problem Statement  
With the increasing popularity and accessibility of AI chatbots, models like **ChatGPT** and **DeepSeek** have emerged as prominent tools for users across diverse domains. While these tools offer extensive capabilities, they are not infallible. Specifically, we focus on **ChatGPT-4 Turbo** and **DeepSeek Chat 1.5**, evaluating which model performs more reliably across a range of user tasks and metrics.

### Motivation  
The rise of large language models (LLMs) has sparked significant interest in developing AI systems capable of answering any query accurately and efficiently. While ChatGPT and DeepSeek have demonstrated impressive capabilities, their architectures, training paradigms, and performance can vary significantly. This project aims to evaluate and compare these models to better understand their individual strengths, limitations, and potential future developments in the field of generative AI.

## Methodology  

We utilize a large **Kaggle dataset** containing a series of queries posed to both ChatGPT and DeepSeek. Each query entry includes several evaluation metrics:
- Number of tokens used
- Response time
- User-generated rating
- Response accuracy
- Additional metadata

To analyze this dataset, we take the following approach:
- **Attribute Weighting**: Metrics such as accuracy will be given more importance than secondary metrics like response time.
- **Supervised Learning**: Use part of the dataset for training a **K-Nearest Neighbors (KNN)** classifier and apply **Principal Component Analysis (PCA)** for dimensionality reduction to predict response quality on the test set.
- **Unsupervised Learning**: Apply **clustering algorithms** to group similar queries and identify whether certain types of queries are better handled by one model over the other.

This multifaceted approach allows us to assess not only which model performs better overall, but also under what circumstances each model may excel or fail.

## Research Questions

- **Overall Performance:** How do ChatGPT and DeepSeek compare in terms of overall performance metrics (e.g., accuracy or user satisfaction scores)? Which model performs better on average, and is this difference statistically significant?
- **Performance by Query Type:** Do the models have varying performance across different categories or types of queries? For example, does one model excel in certain topics or tasks while the other struggles, or vice versa?
- **Shared Strengths/Weaknesses:** Are there patterns in how the models perform on the same queries? Do they tend to succeed on the same queries and fail on the same queries (indicating certain queries are inherently easy or hard for both), or does one model often succeed where the other fails?
- **Impact of Query Characteristics:** How do characteristics of the queries (such as query length or complexity) affect each model’s performance? Are differences between ChatGPT and DeepSeek correlated with these query attributes (e.g., do longer or more complex queries favor one model over the other)?
- **Hidden Patterns in Data:** Can we discover any hidden trends or groupings in the dataset using unsupervised techniques? For instance, by applying clustering or PCA, can we identify clusters of interactions with similar outcomes (such as a cluster of queries where one model consistently outperforms the other, or clusters corresponding to distinct difficulty levels)?

## Related Works  

The following studies have conducted similar comparative evaluations:
- **Jiang, Q., Gao, Z., & Karniadakis, G. E.** (2025). *DeepSeek vs. ChatGPT vs. Claude: A Comparative Study for Scientific Computing and Scientific Machine Learning Tasks*. [arXiv:2502.17764](https://arxiv.org/abs/2502.17764)
- **Manik, M. M. H.** (2025). *ChatGPT vs. DeepSeek: A Comparative Study on AI-Based Code Generation*. [arXiv:2502.18467](https://arxiv.org/abs/2502.18467)
- **Shakya, R., Vadiee, F., & Khalil, M.** (2025). *A Showdown of ChatGPT vs DeepSeek in Solving Programming Tasks*. [arXiv:2503.13549](https://arxiv.org/abs/2503.13549)

These works provide a valuable foundation and context for our study, particularly in specific application domains such as programming and scientific computation.

---

## Getting Started

### 📦 Environment Setup

To create a reproducible environment for this project, we use Conda and the provided `environment.yml` file.

#### 1. Install Conda
If you don't already have Conda installed, install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/).

#### 2. Clone the repository
```bash
git clone https://github.com/San68bot/beyond-the-prompt.git
cd beyond-the-prompt
```

#### 3. Create the environment
```bash
conda env create -f environment.yml
```

#### 4. Activate the environment
```bash
conda activate beyond-the-prompt
```

#### 5. Enable Jupyter kernel
```bash
python -m ipykernel install --user --name=beyond-the-prompt
```

#### 6. Updating the environment (only when changes are made to `environment.yml`)
```bash
conda env update --file environment.yml --prune
```