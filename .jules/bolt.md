## 2026-10-29 - Optimize MultiheadAttention
**Learning:** By default, nn.MultiheadAttention computes and returns attention weights. Passing need_weights=False avoids this computation, saving memory and enabling FlashAttention when available.
**Action:** Always check if attention weights are actually used. If they are discarded downstream (e.g. named `_`), pass need_weights=False in the forward pass to improve performance.
