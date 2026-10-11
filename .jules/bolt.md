## 2024-10-11 - PyTorch MultiheadAttention Optimization
**Learning:** In PyTorch's `nn.MultiheadAttention`, if the attention weights are not explicitly needed downstream, passing `need_weights=False` avoids computing and allocating memory for them, which enables FlashAttention (faster path) under the hood.
**Action:** Always check if attention weights are unpacked and used downstream. If they are ignored/unused, set `need_weights=False` to optimize performance.
