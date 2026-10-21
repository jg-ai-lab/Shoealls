## 2026-10-21 - PyTorch MultiheadAttention Optimization
**Learning:** In PyTorch, `nn.MultiheadAttention` computes and returns attention weights by default, which consumes unnecessary computation and memory.
**Action:** When attention weights are not explicitly needed downstream (and discarded via `_`), pass `need_weights=False` to enable potential optimizations like FlashAttention.
