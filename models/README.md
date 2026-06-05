# models/ — Saved model fits and result metadata

Outputs of the model notebooks, organized by pipeline. Each pipeline folder contains two subfolders: `fits/` holds the trained model files, and `json/` holds the result metadata that the comparison notebooks read.

| Subdirectory | Description |
|---|---|
| `text/` | Fits and metadata for the seven text models. See `text/README.md`. |
| `images/` | Fits and metadata for the four image models. See `images/README.md`. |
| `both/` | Fits and metadata for the multimodal fusion models. See `both/README.md`. |

## Conventions

- scikit-learn models are saved as `.pkl`; Keras (TensorFlow) models as `.keras`.
- Every model writes a `<model>_meta.json` to its pipeline's `json/` folder, containing accuracy, macro F1, per-class F1, and runtime (runtime includes hyperparameter tuning).
- The comparison notebooks load the `json/` metadata automatically, so model fits do not need to be reloaded to regenerate the comparison tables and charts.
