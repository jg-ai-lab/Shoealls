## 2026-11-06 - Enable FlashAttention in MultiheadAttention
**Learning:** PyTorch computes attention weights by default in `nn.MultiheadAttention`. When these weights are not used downstream, it unnecessarily allocates memory and prevents the use of optimized FlashAttention kernels.
**Action:** Always set `need_weights=False` in `nn.MultiheadAttention` calls if the returned weights (the second output) are discarded, in order to save memory and speed up the forward pass.
