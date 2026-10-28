## 2026-10-27 - [MultiheadAttention FlashAttention optimization]
**Learning:** PyTorch nn.MultiheadAttention calculates attention weights by default, which disables the FlashAttention fastpath and increases memory/computation. Setting need_weights=False when weights are unused (_ or discarded) enables FlashAttention.
**Action:** Always set need_weights=False on nn.MultiheadAttention calls when the returned attention weights are not explicitly unpacked and used downstream.
