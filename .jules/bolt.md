## 2026-10-31 - PyTorch MultiheadAttention Optimization
**Learning:** By default, PyTorch's `nn.MultiheadAttention` computes and returns attention weights. When these weights are discarded (unpacked as `_`), it wastes computation and memory, and prevents the use of efficient attention backends like FlashAttention.
**Action:** Explicitly set `need_weights=False` in the `forward` pass of `MultiheadAttention` when attention weights are not needed (e.g., in `src/models/fusion.py`). Note that this cannot be used if downstream logic requires the weights (e.g., reasoning engines).
