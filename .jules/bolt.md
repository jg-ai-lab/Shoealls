## 2026-10-23 - Optimize MultiheadAttention for FlashAttention
**Learning:** When using PyTorch's `nn.MultiheadAttention`, if the attention weights are discarded (assigned to `_`), setting `need_weights=False` prevents unnecessary computation and memory allocation, and enables FlashAttention when supported.
**Action:** Always check if attention weights are actually unpacked and used downstream. If unused, set `need_weights=False` and name the target `_` to optimize performance.
