## 2023-10-24 - PyTorch MultiheadAttention FlashAttention Optimization
**Learning:** PyTorch's `nn.MultiheadAttention` allocates memory and computes attention weights by default, which disables FlashAttention. When attention weights are discarded, this creates unnecessary overhead.
**Action:** Always set `need_weights=False` in `nn.MultiheadAttention` forward calls when the returned attention weights are ignored (e.g. unpacked into `_`).
