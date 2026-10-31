# Data card — Darija to English parallel sentences (Phase 1)

Built on 2026-10-31 with seed 42. Code: `notebooks/01_data_audit.ipynb`.

## Sources (check licences yourself before redistributing anything)
- DODa via `atlasia/darija_english`, config `doda` (Darija Open Dataset). Darija is written in Latin letters (Arabizi). The GitHub README allows research, personal and educational use; the Hugging Face copy may carry CC-BY-NC-4.0.
- Sources used in this run: doda.

## Cleaning funnel
| step | doda | total |
|---|---|---|
| 0. loaded rows | 45103 | 45103 |
| 1. non-empty | 44713 | 44713 |
| 2. quality flag (if any) | 44713 | 44713 |
| 3. no URL / e-mail | 44713 | 44713 |
| 4. Darija is Latin script (Arabizi) | 44663 | 44663 |
| 5. English is Latin script | 44620 | 44620 |
| 6. not mostly digits | 44530 | 44530 |
| 7. length in bounds | 15067 | 15067 |
| 8. length ratio | 15040 | 15040 |
| 9. duplicate Darija sentence | 14996 | 14996 |
| 10. valid English key | 14996 | 14996 |

## Splits ((0.7, 0.15, 0.15) requested)
| split | doda | total |
|---|---|---|
| train | 10498 | 10498 |
| dev | 2249 | 2249 |
| test | 2249 | 2249 |

- Splits are grouped by English sentence and deduplicated on the Darija sentence, so no sentence leaks between train, dev and test.
- Out-of-vocabulary rate of dev/test words w.r.t. train: {'dev': {'darija': 0.185, 'english': 0.0499}, 'test': {'darija': 0.1859, 'english': 0.0519}}
- Extra clean rows kept for later scaling (never overlapping dev/test): 0

## Known limitations
- Arabizi spelling is not standardised (digits such as 3, 7, 9 stand for Arabic letters, spellings vary), so the out-of-vocabulary rate is high.
- Only Latin-script (Arabizi) Darija is kept; Arabic-script rows are filtered out.
- About 0.0% of kept Darija sentences contain Arabic-script letters (mixed script).
