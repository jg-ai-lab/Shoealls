## 2024-10-16 - [FlashAttention Optimization in PyTorch]
**Learning:** When using PyTorch's `nn.MultiheadAttention`, if attention weights are discarded (unpacked to `_`), we should set `need_weights=False` to prevent unnecessary computation and memory allocation, enabling FlashAttention.
**Action:** Always check `nn.MultiheadAttention` forward passes; if weights are unused, set `need_weights=False`.
