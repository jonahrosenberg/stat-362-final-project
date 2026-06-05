# data/ — Dataset

The Twitter Dataset for Sentiment Analysis (Kaggle), ~4,869 real tweets. Each tweet is paired: it has both a text caption and a corresponding image, linked by a numeric file ID and sharing one sentiment label.

| File / Directory | Description |
|---|---|
| `LabeledText.csv` | The text and labels. Read with `encoding='latin-1'`. Columns: `File Name` (the pairing key, e.g. `1.txt`), `Caption` (the tweet text), and `LABEL` (negative / neutral / positive). 4,869 rows. |
| `glove.6B.100d.txt` | Pretrained GloVe word embeddings (100-dimensional, trained on 6 billion tokens), used to initialize the GloVe+LSTM model. ~822 MB, gitignored — download separately from https://nlp.stanford.edu/projects/glove/. |
| `Images/` | The tweet images, split across three class subfolders. See `Images/README.md`. Gitignored due to size. |

## Pairing

`File Name` is the join key between the two modalities: `1.txt` in the CSV corresponds to the image `1.jpg` in the class subfolder matching that tweet's label. The multimodal pipeline relies on this pairing to align each caption with its image.

## Labels

| Class | Count | Share |
|---|---|---|
| Neutral | 1,771 | 36.4% |
| Positive | 1,646 | 33.8% |
| Negative | 1,452 | 29.8% |
| Total | 4,869 | 100% |
