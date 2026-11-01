## 2026-11-01 - Enable FlashAttention in PyTorch MultiheadAttention
**Learning:** When using PyTorch's `nn.MultiheadAttention`, setting `need_weights=False` during the forward pass prevents unnecessary computation and memory allocation if attention weights are discarded (enabling FlashAttention).
**Action:** Always verify if attention weights are explicitly unpacked and used downstream. If they are discarded (e.g., assigned to `_`), explicitly set `need_weights=False` and add an explanatory comment to safely enable FlashAttention memory optimizations.
