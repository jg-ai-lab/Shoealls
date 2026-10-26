## 2024-10-26 - [FlashAttention enabling]
**Learning:** PyTorch's MultiheadAttention computes attention weights by default. When these weights are unused (e.g. they are ignored with `_`), setting `need_weights=False` significantly improves performance by enabling FlashAttention under the hood, speeding up operations up to ~40% for larger batches.
**Action:** Always set `need_weights=False` when calling `nn.MultiheadAttention` if the attention weights are not explicitly required for downstream logic.
