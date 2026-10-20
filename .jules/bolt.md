## 2025-02-23 - PyTorch MultiheadAttention Memory and Compute Optimization
**Learning:** When using PyTorch's `nn.MultiheadAttention` and the attention weights are discarded downstream, setting `need_weights=False` prevents unnecessary computation and memory allocation. It also enables FlashAttention.
**Action:** Always set `need_weights=False` in `nn.MultiheadAttention` forward passes when the returned weights (second output) are mapped to `_` and not explicitly used downstream, while adding a comment explaining the optimization.
