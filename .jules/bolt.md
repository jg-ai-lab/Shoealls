## 2024-10-13 - PyTorch MultiheadAttention Optimization
**Learning:** By default, `nn.MultiheadAttention` in PyTorch computes and returns attention weights. When these weights are not needed (e.g., in fusion layers where only the output representation matters), computing them wastes memory and computation, and prevents the use of FlashAttention.
**Action:** When using `nn.MultiheadAttention`, explicitly set `need_weights=False` unless the attention weights are actually unpacked and used downstream. Rename the unused output variable to `_`.
