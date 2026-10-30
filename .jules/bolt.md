## 2026-10-30 - Optimize MultiheadAttention weights computation
**Learning:** PyTorch's `nn.MultiheadAttention` computes and returns attention weights by default, which takes memory and time. In this codebase, the attention weights are not always used. When discarded, this creates an unnecessary bottleneck.
**Action:** When `need_weights=False` is set during the forward pass of `nn.MultiheadAttention`, PyTorch avoids allocating and computing the attention weights tensor, saving computation and memory. Do this wherever the weights tensor is thrown away.
