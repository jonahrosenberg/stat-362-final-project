# STAT 362 Final Project — Sentiment Analysis of Tweets: Text, Images, and Both

A multimodal machine-learning study that asks: for a tweet that comes with both a caption and an image, which representation carries the most predictable sentiment — the text, the image, or the two combined? Three parallel classification pipelines (text-only, image-only, and multimodal fusion) are built on the same ~4,869 paired tweets and compared on identical terms. Each predicts one of three sentiment classes (negative, neutral, positive).

Headline result: text wins (GloVe+LSTM, 73.3%), the image models plateau near the 36.3% majority-class baseline because sentiment usually lives in overlaid caption text a CNN cannot read, and multimodal fusion matches but never exceeds text.

## Top-level files

| File | Description |
|---|---|
| `Rosenberg_Jonah_report.ipynb` | The final report notebook, written for Quarto rendering (sections: Introduction, Data, Methods, Results, Conclusion, References). Code is hidden on render; a GitHub link is provided in the preamble. |
| `Rosenberg_Jonah_report.html` | The rendered, self-contained HTML report. |
| `STAT362_Final_Presentation.pptx` | An 8-slide presentation deck (native, fully editable objects). |
| `STAT362_Final_Project_Description.pdf` | The assignment specification. |
| `.gitignore` | Git exclusions (virtual env, large data, etc.). |

## Directories

| Directory | Description |
|---|---|
| `text/` | The text-only pipeline: EDA, preprocessing, and seven model notebooks plus a comparison. |
| `images/` | The image-only pipeline: EDA, preprocessing, and four model notebooks plus a comparison. |
| `both/` | The multimodal pipeline: three late-fusion notebooks and a cross-pipeline comparison. |
| `models/` | Saved trained model fits and result metadata, organized by pipeline. |
| `data/` | The dataset: the labeled-text CSV, GloVe embeddings, and the paired images. |

## Environment

- `.venv/` — Python 3.14 virtual environment for all non-TensorFlow notebooks (pandas, scikit-learn, nltk, matplotlib, seaborn).
- Anaconda — used for all TensorFlow notebooks (TensorFlow supports Python ≤ 3.12): the RNN and GloVe+LSTM text models, all image CNN notebooks, and all three fusion notebooks.
- Run a notebook: `.venv\Scripts\jupyter.exe nbconvert --to notebook --execute --inplace <notebook>.ipynb`
- Render the report: `quarto render Rosenberg_Jonah_report.ipynb`

## Pipeline at a glance

| Pipeline | Best model | Test accuracy |
|---|---|---|
| Text | GloVe+LSTM | 73.3% |
| Multimodal | Stacking | 70.7% |
| Image | MobileNetV2 | 41.9% |
| (Reference) | Majority-class baseline | 36.3% |

See each subdirectory's `README.md` for a file-by-file description.
