## 2026-10-28 - [MultiheadAttention Memory Optimization]
**Learning:** PyTorch's MultiheadAttention computes attention weights by default, which consumes memory and computation even if discarded. Disabling this via need_weights=False prevents unnecessary allocation (and enables FlashAttention) when attention weights are not needed.
**Action:** Always set need_weights=False when calling nn.MultiheadAttention if the returned attention weights are not unpacked and used downstream.
