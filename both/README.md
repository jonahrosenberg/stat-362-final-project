# both/ — Multimodal pipeline and cross-pipeline comparison

The multimodal pipeline combines the best text model (GloVe+LSTM) and best image model (MobileNetV2) by late fusion of their softmax probabilities. Unlike the unimodal pipelines, these notebooks build one combined DataFrame (joining caption to image by numeric ID) and perform a single joint train/test split, so both base models are trained and evaluated on exactly the same tweets. Fits and metadata are written to `../models/both/`. All fusion notebooks use TensorFlow and must run in Anaconda; the comparison notebook runs in `.venv`.

| File | Description |
|---|---|
| `05_multimodal_late_fusion.ipynb` | Equal-average fusion: averages the text and image probability vectors. 67.7% accuracy (joint test). Run in Anaconda. |
| `05_multimodal_weighted_fusion.ipynb` | Weighted-average fusion: `α·text + (1−α)·image`, with α tuned on a held-out validation set (base models trained on `train` only). 69.5% accuracy. Run in Anaconda. |
| `05_multimodal_stacking.ipynb` | Stacking: a logistic-regression meta-classifier on the concatenated 6-dim probability vector. 70.7% accuracy, exactly matching text-only on the joint split. Run in Anaconda. |
| `06_full_model_comparison.ipynb` | Cross-pipeline comparison of every model (text + image + multimodal). Loads metadata from all three `../models/*/json/` folders, tags each by pipeline, and produces combined tables and charts. Run in `.venv`. |

The numbering keeps the comparison (`06_`) above the fusion models (`05_`) it compares, matching the project's convention.
