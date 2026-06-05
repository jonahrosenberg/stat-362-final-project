# images/ — Image-only pipeline

Models trained on the tweet image only, each resized to 128×128 RGB. Same notebook numbering as the text pipeline (`01_` EDA, `02_` preprocessing, `03_` peer models, `04_` comparison) and the same locked split. Trained fits and metadata are written to `../models/images/`. All convolutional notebooks use TensorFlow and must run in Anaconda.

| File | Description |
|---|---|
| `01_eda_images.ipynb` | Exploratory analysis of the images: class balance, resolution mix, and the photo / meme / screenshot composition. |
| `02_image_pipeline.ipynb` | Shared image preprocessing: builds the path/label table, loads and resizes images to 128×128, and demonstrates the train/test split. |
| `03_baseline.ipynb` | Majority-class baseline (always predicts neutral). 36.3% accuracy. |
| `03_cnn_scratch.ipynb` | Convolutional network trained from scratch. 36.3% accuracy (collapses to the majority class). Run in Anaconda. |
| `03_cnn_mobilenet.ipynb` | MobileNetV2 transfer learning with a frozen ImageNet backbone (best `dense_units=256`). 41.9% accuracy (best image model). Run in Anaconda. |
| `03_cnn_efficientnet.ipynb` | EfficientNetB0 transfer learning; uses `validation_split=0.2` for early stopping. 36.9% accuracy. Run in Anaconda. |
| `04_model_comparison.ipynb` | Loads all `../models/images/json/*_meta.json` and produces the comparison tables and charts. Run in `.venv`. |

A logistic regression on raw flattened pixels was attempted but cut for time (too slow on ~49,000 dense features); it is discussed in the report rather than kept as a notebook.
