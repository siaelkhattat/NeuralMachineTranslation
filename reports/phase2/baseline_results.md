# Method A baseline results

| system | dev_bleu | dev_chrfpp | test_bleu | test_chrfpp |
|---|---|---|---|---|
| A0 (no fine-tuning) | 0.19 | 8.35 | 0.21 | 8.56 |
| A1 (mean ± std over 3 seeds) | 30.61 ± 0.36 | 48.22 ± 0.21 | 30.81 ± 0.15 | 48.22 ± 0.24 |

Per seed:

| system | seed | dev_bleu | dev_chrfpp | test_bleu | test_chrfpp |
|---|---|---|---|---|---|
| A0 (no fine-tuning) | - | 0.19 | 8.35 | 0.21 | 8.56 |
| A1 (fine-tuned) | 13 | 30.18 | 47.95 | 30.61 | 47.93 |
| A1 (fine-tuned) | 42 | 31.06 | 48.46 | 30.86 | 48.21 |
| A1 (fine-tuned) | 2024 | 30.58 | 48.24 | 30.96 | 48.52 |
