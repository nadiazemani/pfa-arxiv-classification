# Scientific Domain Classification from arXiv Articles

First-year final project (PFA) at **ENSIAS (Rabat)**, Artificial Intelligence track.
End-to-end pipeline: arXiv data collection -> NLP preprocessing -> exploratory analysis -> class rebalancing -> ML/DL models -> Streamlit demo.

## Categories
`cs.AI`, `cs.LG`, `econ.EM`, `math.AP`, `physics.med-ph`, `q-bio.QM`

## Contents
- `arxiv_article_classification.ipynb`: main notebook (designed for Google Colab)
- `requirements.txt`: dependencies

## Pipeline
1. Scraping with the `arxiv` API (about 5,600 articles)
2. Preprocessing: cleaning, NLTK stopwords, TF-IDF
3. Exploratory analysis (class distribution, word clouds, publication trends)
4. Rebalancing with `RandomOverSampler`
5. Models: Logistic Regression, Random Forest, SVM, Naive Bayes, LSTM, XGBoost, BERT embeddings
6. Streamlit app (served through ngrok on Colab)

## Results (test set, 1,120 articles)
| Model | Accuracy |
|---|---|
| SVM | ~0.82 |
| Logistic Regression | ~0.82 |
| XGBoost | ~0.80 |
| Random Forest | ~0.77 |

`cs.LG` is the hardest class (close to `cs.AI`). The simple LSTM trained in the notebook did not learn (about 18% accuracy, close to chance) and is kept for reference only.

## Usage
```bash
pip install -r requirements.txt
jupyter notebook arxiv_article_classification.ipynb
```
CSV and `.pkl` files are not included: re-run the scraping and training cells to generate them. The stored cell outputs come from the original runs and some log lines are still in French; re-run the notebook to regenerate them in English.
For the Streamlit interface on Colab, a personal ngrok token is requested (never publish it).

## Author
Nadia Zemani - ENSIAS Rabat
