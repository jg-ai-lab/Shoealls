## 2024-03-24 - Initial setup
**Learning:** Initializing journal.
**Action:** None.

## 2024-10-25 - Optimize MultiheadAttention
**Learning:** By default `nn.MultiheadAttention` calculates and returns attention weights. Passing `need_weights=False` prevents unnecessary computation and memory allocation when the weights are unused, potentially enabling FlashAttention.
**Action:** When using `nn.MultiheadAttention` and not explicitly using the attention weights downstream, set `need_weights=False` to save compute and memory.
