
## Summary

**Context**
- Concept Bottleneck Models rely on the quality of the concept banks. 

**Solution**
- Similar to [[Incremental Residual Concept Bottleneck Models]]: Have learnable vectors to account for unseen concepts. The difference maybe in the view of these learnable vectors:
	- [[Incremental Residual Concept Bottleneck Models]]: these vectors are concepts of the images that are missed during image-concept lookup, and they are computed from the image embeddings. 
	- This: the learnable vectors are general concepts that are missed in the concept banks. After training, they are translated to concepts using a concept translator model.