# Experiment Context

## Objective
- Primary goal:
- Target BPB:
- Artifact size target:
- Deadline:

## Current Baseline
- Script:
- Last known BPB:
- Last known artifact size:
- Hardware:
- Tokenizer + dataset variant:

## Active Run Configuration
- Run ID:
- Branch/commit:
- Script path:
- Key env vars:
  - ITERATIONS=
  - TRAIN_BATCH_TOKENS=
  - TRAIN_SEQ_LEN=
  - MATRIX_LR=
  - SCALAR_LR=
  - TIED_EMBED_LR=
  - MUON_MOMENTUM=
  - WARMUP_STEPS=
  - WARMDOWN_ITERS=
  - MAX_WALLCLOCK_SECONDS=

## Architecture Notes
- Model shape:
- Recurrence/skip behavior:
- Quantization strategy:
- Any non-default eval settings:

## Latest Results
- Date/time:
- Train stop step/time:
- Final val_loss:
- Final val_bpb:
- Roundtrip metric line:
- Sliding window metric line (if used):
- Artifact bytes:
- Under/over 16,000,000 bytes:

## Previous Log Summary
Important: These are NOT my models; they are competitor submissions from repository logs and are used only for reference.

| Model / Run | Compressed Size (bytes) | Score (val_bpb) | Under/Over 16,000,000 | Rank by Score |
|---|---:|---:|---:|---:|
| 2026-03-19_WarmdownQuantization | 15924148 | 1.17890201 | -75852 | 1 |
| 2026-03-19_smeargate_orthoinit_muonwd | 15817180 | 1.18908459 | -182820 | 2 |
| 2026-03-19_SlidingWindowEval | 15816489 | 1.19250007 | -183511 | 3 |
| 2026-03-19_int6_STE QAT_ MLP_bigram _U_Net | 16127834 | 1.19312169 | 127834 | 4 |
| 2026-03-19_MixedQuant_Int6Int8_SlidingWindow | 15296720 | 1.19650941 | -703280 | 5 |
| 2026-03-19_MLP3x_QAT_Int6_SlidingWindow | 15637847 | 1.19979073 | -362153 | 6 |
| 2026-03-19_TrainingOptSeq4096 | 15820684 | 1.20143417 | -179316 | 7 |
| 2026-03-18_LongContextSeq2048 | 15819554 | 1.20576485 | -180446 | 8 |
| 2026-03-18_Quasi10Bfrom50B_SP1024_9x512_KV4_4h_pgut3 | 15762519 | 1.20737944 | -237481 | 9 |
| 2026-03-19_10L_MixedPrecision | 15879916 | 1.21474500 | -120084 | 10 |
| 2026-03-18_FP16Embed_WD3600 | 15848097 | 1.21972502 | -151903 | 11 |
| 2026-03-18_LowerLR | 15803327 | 1.22296644 | -196673 | 12 |
| 2026-03-17_NaiveBaseline | 15815847 | 1.22436570 | -184153 | 13 |

## Changes Since Last Good Run
- Change 1:
- Change 2:
- Change 3:

## Hypotheses
- Hypothesis A:
- Hypothesis B:
- Hypothesis C:

## Next Actions
1. 
2. 
3. 

## Open Questions
- 
- 
- 

## Useful Log Snippets
- 
- 
- 
