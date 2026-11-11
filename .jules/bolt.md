## 2026-11-11 - Enable FlashAttention by discarding unused attention weights
**Learning:** PyTorch's nn.MultiheadAttention computes attention weights by default, which disables FlashAttention and consumes memory.
**Action:** When using nn.MultiheadAttention where the attention weights are not needed (unpacked and ignored as `_`), explicitly set `need_weights=False` in the forward pass to enable FlashAttention and save compute.
