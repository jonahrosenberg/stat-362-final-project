# models/both/json/ — Multimodal result metadata

One `*_meta.json` per fusion strategy, written by the `05_*` notebooks and read by `both/06_full_model_comparison.ipynb`. In addition to the standard fields (`model`, `accuracy`, `macro_f1`, per-class F1, `runtime_seconds`), these files also record `text_acc_joint_test` and `img_acc_joint_test` (the base models' accuracy on the same joint split) plus strategy-specific fields such as `best_alpha` (weighted) and the meta-classifier coefficient sums (stacking).

| File | Strategy | Accuracy (joint test) |
|---|---|---|
| `late_fusion_meta.json` | Equal average | 67.7% |
| `weighted_fusion_meta.json` | Weighted average (α tuned on validation) | 69.5% |
| `stacking_meta.json` | Logistic-regression stacking | 70.7% |

All three land at or below the text-only accuracy on the joint split; stacking matches it exactly.
