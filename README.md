# ChatGPT Vs. DeepSeek: Battle of the Bots  
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

## Related Works  

The following studies have conducted similar comparative evaluations:
- **Jiang, Q., Gao, Z., & Karniadakis, G. E.** (2025). *DeepSeek vs. ChatGPT vs. Claude: A Comparative Study for Scientific Computing and Scientific Machine Learning Tasks*. [arXiv:2502.17764](https://arxiv.org/abs/2502.17764)
- **Manik, M. M. H.** (2025). *ChatGPT vs. DeepSeek: A Comparative Study on AI-Based Code Generation*. [arXiv:2502.18467](https://arxiv.org/abs/2502.18467)
- **Shakya, R., Vadiee, F., & Khalil, M.** (2025). *A Showdown of ChatGPT vs DeepSeek in Solving Programming Tasks*. [arXiv:2503.13549](https://arxiv.org/abs/2503.13549)

These works provide a valuable foundation and context for our study, particularly in specific application domains such as programming and scientific computation.