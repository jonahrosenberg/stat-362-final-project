# models/images/json/ — Image result metadata

One `*_meta.json` per image model, written by the `03_*` notebooks and read by `04_model_comparison.ipynb` and `both/06_full_model_comparison.ipynb`. Each file holds `model`, `accuracy`, `macro_f1`, `negative_f1`, `neutral_f1`, `positive_f1`, and `runtime_seconds`.

| File | Model | Accuracy |
|---|---|---|
| `baseline_meta.json` | Majority-class baseline | 36.3% |
| `cnn_scratch_meta.json` | CNN from scratch | 36.3% |
| `cnn_mobilenet_meta.json` | MobileNetV2 | 41.9% |
| `cnn_efficientnet_meta.json` | EfficientNetB0 | 36.9% |
