## 2026-11-02 - Prevent MultiheadAttention Unnecessary Work
**Learning:** PyTorch's `nn.MultiheadAttention` by default computes and returns attention weights even if they aren't used, allocating memory and increasing computation overhead.
**Action:** When using `nn.MultiheadAttention`, add `need_weights=False` if the weights are discarded downstream.
