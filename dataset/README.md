# Dataset 

This repository uses publicly available datasets to train and evaluate two **Deep Learning models** in the restaurant review domain:

- **Sentiment Analysis (SA)**
- **Named Entity Recognition (NER)**

The datasets are organized in a structured manner to ensure reproducibility and compatibility with the training pipelines provided in this project.

---

## Data Sources & Credits

All datasets used in this project are sourced from public repositories. Full credit is given to the original authors and contributors.

### Named Entity Recognition (NER)

- **Dataset Name:** MIT Restaurant Corpus
- **Description:** Annotated restaurant-related queries with entity labels (e.g., food, price, location)
- **🔗Source:** Kaggle – MIT Restaurant Corpus CRF Dataset
  [https://www.kaggle.com/datasets/marusagar/mit-restaurant-corpus-crf-dataset](https://www.kaggle.com/datasets/marusagar/mit-restaurant-corpus-crf-dataset)

### Sentiment Analysis (SA)

- **Dataset Name:** Restaurant Reviews Dataset
- **Description:** Customer reviews annotated with binary sentiment labels (positive / negative)
- **🔗Source:** GitHub – Restaurant Reviews Sentiment Analysis
  [https://github.com/aadimangla/Restaurant-Reviews-Sentiment-Analysis/blob/master/Dataset/Restaurant_Reviews.tsv](https://github.com/aadimangla/Restaurant-Reviews-Sentiment-Analysis/blob/master/Dataset/Restaurant_Reviews.tsv)


---

## 🗂️ Dataset Directory Structure

Ensure that all dataset files follow the directory structure below. This structure is required for the training and evaluation scripts to run correctly.

```
dataset/
├── ner/
│   ├── label_train.txt      # BIO entity labels for training data
│   ├── label_test.txt       # BIO entity labels for test data
│   ├── sent_train.txt       # Sentences for training data
│   └── sent_test.txt        # Sentences for test data
│
└── sa/
    ├── Restaurant_Reviews.csv  # Sentiment dataset (CSV format)
    └── Restaurant_Reviews.tsv  # Sentiment dataset (TSV format)
```

---

## Sentiment Analysis (SA) Dataset

The Sentiment Analysis dataset contains customer-written restaurant reviews labeled with sentiment polarity.

**Location:** `dataset/sa/`

**Formats Available:**

- CSV (`Restaurant_Reviews.csv`)
- TSV (`Restaurant_Reviews.tsv`)

**Schema:**

| Column Name | Description                                  |
| ----------- | -------------------------------------------- |
| Review      | Text content of the restaurant review        |
| Liked       | Sentiment label (0 = Negative, 1 = Positive) |

This dataset is used to train a binary text classification model based on transformer architectures.

---

## Named Entity Recognition (NER) Dataset

The NER dataset is designed to identify and classify restaurant-related entities within text, such as food items, pricing information, locations, and services.

**Location:** `dataset/ner/`

**Format:** Plain text files (`.txt`)

**Data Organization:**

- Sentence files (`sent_*.txt`) contain one sentence per line
- Label files (`label_*.txt`) contain corresponding entity labels per token

**Tagging Scheme:** BIO (Beginning, Inside, Outside)

Example:

```
Sentence:  I want cheap sushi in Tokyo
Labels:    O O B-PRICE B-FOOD O B-LOCATION
```

The sentence and label files are aligned line-by-line to ensure correct token-level supervision during training.

---
