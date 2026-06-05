# models/text/json/ — Text result metadata

One `*_meta.json` per text model, written by the `03_*` notebooks and read by `04_model_comparison.ipynb` and `both/06_full_model_comparison.ipynb`. Each file holds `model`, `accuracy`, `macro_f1`, `negative_f1`, `neutral_f1`, `positive_f1`, and `runtime_seconds`.

| File | Model | Accuracy |
|---|---|---|
| `baseline_meta.json` | Majority-class baseline | 36.3% |
| `naive_bayes_meta.json` | Multinomial naive Bayes | 67.2% |
| `logistic_regression_meta.json` | Logistic regression | 70.0% |
| `svm_meta.json` | Linear SVM | 68.2% |
| `mlp_text_meta.json` | Multilayer perceptron | 66.4% |
| `rnn_text_meta.json` | Plain RNN | 38.3% |
| `glove_rnn_text_meta.json` | GloVe+LSTM | 73.3% |
