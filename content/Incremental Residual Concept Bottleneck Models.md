
## Summary

**Context**
- Vision language embedding (e.g., clip) allow finding interpretable concepts for each image without training (based on the embedding similarities)
- A lot of focuses were spent on how to construct a good concept bank, but still had the concept completeness issue - can't find all possible concepts.

**Solution**
- Have learnable vectors to account for the (potentially missing) concepts to improve the accuracy of the final classifier (residual bottleneck).
- Have a mechanism to add meaning to these learnable vectors when seeing more samples. 

**Intersting discussion**
- How many concepts are enough? The authors argue that the number of concepts should be lower than than the original dimension d for the concept bottleneck model to be actually a bottleneck model.

Related to:
- [[Concept Embedding Models - Beyond the Accuracy-Explainability Trade-Off]]