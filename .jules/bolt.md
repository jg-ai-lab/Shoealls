## 2026-11-05 - Optimize MultiheadAttention in Fusion Model
**Learning:** When using PyTorch's nn.MultiheadAttention in fusion layers, if the attention weights are not needed downstream (discarded into _), computing them wastes memory and computation, blocking FlashAttention.
**Action:** Explicitly pass need_weights=False to nn.MultiheadAttention forward calls to enable FlashAttention and save memory/compute when attention weights are unused.
