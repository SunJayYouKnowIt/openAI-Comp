Run 3
    stopping_early: wallclock_cap train_time:600038ms step:13780/20000
    peak memory allocated: 10184 MiB reserved: 10200 MiB
    Serialized model: 67224983 bytes
    Code size: 47642 bytes
    Total submission size: 67272625 bytes
    Serialized model int8+zlib: 15815847 bytes (payload:17178912 raw_torch:17224025 payload_ratio:3.91x)
    Total submission size int8+zlib: 15863489 bytes
    final_int8_zlib_roundtrip val_loss:2.0727 val_bpb:1.2244 eval_time:1401ms
    final_int8_zlib_roundtrip_exact val_loss:2.07269931 val_bpb:1.22436570

Run 2
    stopping_early: wallclock_cap train_time:600037ms step:6709/20000
    peak memory allocated: 18871 MiB reserved: 18976 MiB
    swa:applying averaged 24 checkpoints
    Serialized model: 98437419 bytes
    Code size: 52930 bytes
    Total submission size: 98490349 bytes
    Serialized model int6+zstd: 15913048 bytes
    Total submission size int8+zlib: 15965978 bytes
    final_eval_mode:sliding_window stride:64 batch_seqs:32
    final_int8_zlib_roundtrip val_loss:1.9294 val_bpb:1.1427 eval_time:168421ms
    final_int8_zlib_roundtrip_exact val_loss:1.92941613 val_bpb:1.14271194

Run 1
    stopping_early: wallclock_cap train_time:600034ms step:6713/20000
    peak memory allocated: 18871 MiB reserved: 18976 MiB
    swa:applying averaged 24 checkpoints
    Serialized model: 98437419 bytes
    Code size: 52930 bytes
    Total submission size: 98490349 bytes
    Serialized model int6+zstd: 15631946 bytes
    Total submission size int8+zlib: 15684876 bytes
    final_eval_mode:sliding_window stride:64 batch_seqs:32
    final_int8_zlib_roundtrip val_loss:1.9292 val_bpb:1.1426 eval_time:168368ms
    final_int8_zlib_roundtrip_exact val_loss:1.92923337 val_bpb:1.14260369
