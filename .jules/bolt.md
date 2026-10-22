## 2026-10-22 - [MultiheadAttention Memory Optimization]
**Learning:** In PyTorch's `nn.MultiheadAttention`, when attention weights are discarded (not unpacked and used), setting `need_weights=False` prevents unnecessary computation and memory allocation, enabling FlashAttention.
**Action:** Add `need_weights=False` to `MultiheadAttention` calls where the weights are discarded to optimize memory and speed.
