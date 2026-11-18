# Classification de domaines scientifiques à partir d'articles arXiv (PFA 1ère année)

Projet de fin d'année (PFA) – ENSIAS, filière Intelligence Artificielle.
Pipeline complet : collecte arXiv → prétraitement → analyse exploratoire → rééquilibrage → modèles ML/DL → interface Streamlit.

*Project: classifying arXiv abstracts into 6 scientific domains (scraping, NLP preprocessing, EDA, oversampling, ML/DL models, Streamlit demo).*

## Catégories
`cs.AI`, `cs.LG`, `econ.EM`, `math.AP`, `physics.med-ph`, `q-bio.QM`

## Contenu
- `PFAARXIV_FINALE.ipynb` : notebook principal (conçu pour Google Colab)
- `requirements.txt` : dépendances

## Pipeline
1. Scraping via l'API `arxiv` (~5 600 articles)
2. Prétraitement : nettoyage, stopwords NLTK, TF-IDF
3. Analyse exploratoire (répartition, WordCloud, évolution temporelle)
4. Rééquilibrage par `RandomOverSampler`
5. Modèles : Régression logistique, Random Forest, SVM, Naive Bayes, LSTM, XGBoost, BERT
6. Application Streamlit (via ngrok sur Colab)

## Résultats (test set, 1 120 articles)
| Modèle | Accuracy |
|---|---|
| SVM | ~0.82 |
| Régression logistique | ~0.82 |
| XGBoost | ~0.80 |
| Random Forest | ~0.77 |

La classe `cs.LG` est la plus difficile (proche de `cs.AI`).

## Utilisation
```bash
pip install -r requirements.txt
jupyter notebook PFAARXIV_FINALE.ipynb
```
Les fichiers CSV et `.pkl` ne sont pas inclus : relancez les cellules de scraping et d'entraînement pour les générer.
Pour l'interface Streamlit sur Colab, un jeton ngrok personnel est demandé (ne jamais le publier).

## Auteure
Nadia Zemani – ENSIAS Rabat
