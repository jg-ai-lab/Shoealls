## 2026-11-07 - Optimize MultiheadAttention to prevent unnecessary computation
**Learning:** PyTorch's nn.MultiheadAttention computes and returns attention weights by default. If these weights are not used downstream, setting need_weights=False prevents unnecessary memory allocation and computation.
**Action:** Always set need_weights=False when calling nn.MultiheadAttention if the attention weights are explicitly unpacked and discarded, unless doing so breaks downstream trace/reasoning components.
