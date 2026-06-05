# models/images/fits/ — Trained image models

Saved model fits produced by the `../../../images/03_*` notebooks.

| File | Description |
|---|---|
| `baseline.pkl` | Majority-class dummy classifier. |
| `cnn_scratch.keras` | Convolutional network trained from scratch. |
| `cnn_mobilenet.keras` | MobileNetV2 transfer learning (best image model). |
| `cnn_efficientnet.keras` | EfficientNetB0 transfer learning. |

`.pkl` is a scikit-learn (joblib) save; `.keras` files are Keras/TensorFlow saves.
