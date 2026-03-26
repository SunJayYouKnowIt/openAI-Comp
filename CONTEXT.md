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
- Date/time: 2026-03-25
- Train stop step/time: not provided in pasted snippet
- Final val_loss: 2.38687673
- Final val_bpb: 1.41364285
- Roundtrip metric line: final_int8_zlib_roundtrip_exact val_loss:2.38687673 val_bpb:1.41364285
- Sliding window metric line (if used): final_int8_zlib_roundtrip_exact val_loss:2.56067544 val_bpb:1.51658024
- Artifact bytes: 8096183 (int8+zlib total submission size)
- Under/over 16,000,000 bytes: -7903817 (under by ~7.90 MB)

Additional reported metrics from this run:

- peak memory allocated: 19739 MiB reserved: 20374 MiB
- Serialized model: 45173818 bytes
- Code size: 48581 bytes
- Total submission size: 45222399 bytes
- Serialized model int8+zlib: 8047602 bytes (payload:11634880 raw_torch:11665463 payload_ratio:3.88x)

Compression savings summary:

- Saved vs uncompressed total submission: 37126216 bytes (~37.13 MB)
- Remaining headroom vs 16,000,000-byte cap: 7903817 bytes (~7.90 MB)

Follow-up run saved under baseline entry:

- Serialized model: 67224983 bytes
- Code size: 47686 bytes
- Total submission size: 67272669 bytes
- Serialized model int8+zlib: 12768100 bytes (payload:17178912 raw_torch:17224025 payload_ratio:3.91x)
- Total submission size int8+zlib: 12815786 bytes
- final_int8_zlib_roundtrip val_loss:2.2753 val_bpb:1.3475 eval_time:11106ms
- final_int8_zlib_roundtrip_exact val_loss:2.27525447 val_bpb:1.34753386

Interpretation for this run:

- Under 16,000,000-byte cap by 3184214 bytes (~3.18 MB)

Small sliding-window note:

- final_int8_zlib_roundtrip val_loss:2.5607 val_bpb:1.5166 eval_time:1350230ms
- final_int8_zlib_roundtrip_exact val_loss:2.56067544 val_bpb:1.51658024

## Test 1 (Current Model)

Reported metrics:

- Serialized model: 59861636 bytes
- Code size: 48927 bytes
- Total submission size: 59910563 bytes
- Serialized model int8+zlib: 11213505 bytes (payload:15322336 raw_torch:15357847 payload_ratio:3.91x)
- Total submission size int8+zlib: 11262432 bytes
- final_int8_zlib_roundtrip val_loss:2.2832 val_bpb:1.3522 eval_time:13028ms
- final_int8_zlib_roundtrip_exact val_loss:2.28317788 val_bpb:1.35222654

Cap status:

- Under 16,000,000-byte cap by 4737568 bytes (~4.74 MB)

Architecture delta from prior 6x3 run:

- Prior setup: 6 unique layers, recurrence_steps=3 (effective passes=18), standard recurrent full-stack pass
- Current setup: 7 unique layers with prelude-loop-coda (2 prelude, 3 shared loop repeated 2x, 2 coda), recurrence_steps=2 (effective passes=11)
- Attention KV heads: num_kv_heads changed 4 -> 8
- Attention heads unchanged: num_heads remains 8

Observed metric delta vs prior 6x3 entry (val_bpb 1.34753386, size 12815786):

- val_bpb: 1.34753386 -> 1.35222654 (higher/worse by 0.00469268)
- int8+zlib total size: 12815786 -> 11262432 (smaller by 1553354 bytes, ~1.55 MB)

## Previous Log Summary
Important: These are NOT my models; they are competitor submissions from repository logs and are used only for reference.

| Model / Run                                        | Compressed Size (bytes) | Score (val_bpb) | Under/Over 16,000,000 | Rank by Score |
| -------------------------------------------------- | ----------------------: | --------------: | --------------------: | ------------: |
| 2026-03-19_WarmdownQuantization                   |                15924148 |      1.17890201 |                -75852 |             1 |
| 2026-03-19_smeargate_orthoinit_muonwd             |                15817180 |      1.18908459 |               -182820 |             2 |
| 2026-03-19_SlidingWindowEval                      |                15816489 |      1.19250007 |               -183511 |             3 |
| 2026-03-19_int6_STE QAT_ MLP_bigram _U_Net        |                16127834 |      1.19312169 |                127834 |             4 |
| 2026-03-19_MixedQuant_Int6Int8_SlidingWindow      |                15296720 |      1.19650941 |               -703280 |             5 |
| 2026-03-19_MLP3x_QAT_Int6_SlidingWindow           |                15637847 |      1.19979073 |               -362153 |             6 |
| 2026-03-19_TrainingOptSeq4096                     |                15820684 |      1.20143417 |               -179316 |             7 |
| 2026-03-18_LongContextSeq2048                     |                15819554 |      1.20576485 |               -180446 |             8 |
| 2026-03-18_Quasi10Bfrom50B_SP1024_9x512_KV4_4h_pgut3 |             15762519 |      1.20737944 |               -237481 |             9 |
| 2026-03-19_10L_MixedPrecision                     |                15879916 |      1.21474500 |               -120084 |            10 |
| 2026-03-18_FP16Embed_WD3600                       |                15848097 |      1.21972502 |               -151903 |            11 |
| 2026-03-18_LowerLR                                |                15803327 |      1.22296644 |               -196673 |            12 |
| 2026-03-17_NaiveBaseline                          |                15815847 |      1.22436570 |               -184153 |            13 |

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
