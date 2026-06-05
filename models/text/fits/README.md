# models/text/fits/ — Trained text models

Saved model fits produced by the `../../../text/03_*` notebooks.

| File | Description |
|---|---|
| `baseline.pkl` | Majority-class dummy classifier. |
| `naive_bayes.pkl` | Multinomial naive Bayes on TF-IDF. |
| `logistic_regression.pkl` | Logistic regression on TF-IDF (`C=10`). |
| `svm.pkl` | Linear SVM on TF-IDF (`C=1000`). |
| `mlp_text.pkl` | Multilayer perceptron on TF-IDF. |
| `rnn_text.keras` | Plain RNN with embeddings learned from scratch. |
| `glove_rnn_text.keras` | LSTM with frozen GloVe embeddings (best text model). |

`.pkl` files are scikit-learn (joblib) saves; `.keras` files are Keras/TensorFlow saves.
