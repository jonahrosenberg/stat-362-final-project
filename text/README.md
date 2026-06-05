# text/ — Text-only pipeline

Models trained on the tweet caption only (`Caption` column of `data/LabeledText.csv`). Notebooks are numbered by stage: `01_` EDA, `02_` shared preprocessing, `03_` peer models (any order), `04_` comparison. All models use the locked split `test_size=0.2, random_state=42, stratify=LABEL`. Trained fits and metadata are written to `../models/text/`.

| File | Description |
|---|---|
| `01_eda_text.ipynb` | Exploratory analysis of the captions: class balance, text length, vocabulary, and cleaning effects. |
| `02_text_pipeline.ipynb` | Shared text preprocessing (cleaning, tokenization, TF-IDF / sequence preparation) used by the model notebooks. |
| `03_baseline.ipynb` | Majority-class baseline (always predicts neutral). 36.3% accuracy. |
| `03_naive_bayes.ipynb` | Multinomial naive Bayes on TF-IDF features. 67.2% accuracy. |
| `03_logistic_regression.ipynb` | Logistic regression on TF-IDF (best `C=10`). 70.0% accuracy. |
| `03_svm.ipynb` | Linear SVM on TF-IDF (best `C=1000`). 68.2% accuracy. |
| `03_mlp_text.ipynb` | Multilayer perceptron on TF-IDF. 66.4% accuracy. Run in `.venv`. |
| `03_rnn_text.ipynb` | Plain RNN with embeddings learned from scratch. 38.3% accuracy (collapses). Run in Anaconda. |
| `03_glove_rnn_text.ipynb` | LSTM initialized with frozen GloVe embeddings. 73.3% accuracy (best overall). Run in Anaconda. |
| `04_model_comparison.ipynb` | Loads all `../models/text/json/*_meta.json` and produces the comparison tables and charts. Run in `.venv`. |

Notebooks that use TensorFlow (`03_rnn_text`, `03_glove_rnn_text`) must run in Anaconda; the rest run in `.venv`.
