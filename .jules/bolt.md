## 2026-11-08 - [Enable FlashAttention via need_weights=False]
**Learning:** PyTorch MultiheadAttention computes attention weights by default, but these are often discarded. Passing need_weights=False to MultiheadAttention prevents unnecessary computation and memory allocation and enables optimized paths like FlashAttention when supported.
**Action:** When using MultiheadAttention in PyTorch and discarding the attention weights, pass need_weights=False and use a dummy variable _ for the discarded weights to optimize memory and computation.
