# models/both/fits/ — Multimodal base models

The two base models retrained on the joint multimodal split, saved by `../../../both/05_multimodal_late_fusion.ipynb`. The fusion itself is a lightweight combination of these models' probability outputs and is not saved as a separate file; the weighted and stacking notebooks reproduce their base models at run time.

| File | Description |
|---|---|
| `fusion_text_glove_lstm.keras` | GloVe+LSTM text model trained on the joint split. |
| `fusion_img_mobilenet.keras` | MobileNetV2 image model trained on the joint split. |
