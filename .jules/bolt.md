## 2026-11-10 - Enable FlashAttention by disabling attention weights
**Learning:** By default, PyTorch's MultiheadAttention calculates and returns attention weights. If these weights are not needed downstream, they prevent the use of memory-efficient backends like FlashAttention and allocate unnecessary memory.
**Action:** Always set `need_weights=False` in `nn.MultiheadAttention` forward passes when the attention weights are discarded, enabling FlashAttention and reducing memory usage.
