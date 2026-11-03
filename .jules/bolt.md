## 2026-11-03 - Prevent Unnecessary Memory Allocation in MultiheadAttention
**Learning:** In PyTorch, nn.MultiheadAttention computes and returns attention weights by default, which consumes memory and prevents FlashAttention optimization.
**Action:** When attention weights are unpacked but unused, pass need_weights=False and ensure the unused return variable is named _ (or rename it to _) to save memory and compute.
