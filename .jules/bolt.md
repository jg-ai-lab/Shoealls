## 2024-05-20 - [MultiheadAttention need_weights Optimization]
**Learning:** By default, `nn.MultiheadAttention` in PyTorch computes and returns attention weights. However, if these weights are not used downstream, setting `need_weights=False` prevents unnecessary computation and memory allocation, enabling optimizations like FlashAttention. We should only avoid this if the weights are explicitly unpacked and used.
**Action:** Apply `need_weights=False` when calling `nn.MultiheadAttention` if the attention weights are immediately discarded (e.g., using `_`).
