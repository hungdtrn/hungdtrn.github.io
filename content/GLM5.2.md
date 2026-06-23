## Summary

**Context**
- More efficient, and better open-source for coding agent


**Solution**
- Use index-share (some sort of optimisation on the attention layer) to improve FLOP
- Multi-token prediction (MTP) layers to improve throughput
- Support 1M context window.
- Use a new infra for training and inference (slime).
- Anti-hacking to improve RL. RL tend to find shortcut to achieve the reward (reward-hacking). Detect when the model does that during training and inference.
- Only 1% behind Opus 4.8??? 
	- The comparison use 744B model (800gb+)

