---
title: Mask lower triangle of a Representational Dissimilarity Matrix (RDM)
date: 2020-12-13

tags: [vectorize, flatten, representational similarity, connectivity, rsa, functional connectivity, structural connectivity, rdm, lower triangle, mask, array, matrix]
utilities: [preprocessing]
modalities: [any]
languages: [python]
software: [numpy]

authors: [Shawn Rhoads] 
github_handle: [shawnrhoads]

---

This recipe takes a Representational Dissimilarity Matrix (RDM) as a square numpy array, masks the diagonal and lower triangle, and outputs a flattened numpy array of the upper triangle. 

Easily adaptable for Representational Similarity Analysis (RSA), Functional/Structural Connectivity analyses, or other analyses with related pipelines with symmetric, square matrices.

Requirements:
- [numpy>=1.18.1](https://numpy.org/doc/1.18/)

```py
def flattenRDM(square_matrix):
    assert square_matrix.shape[0] == square_matrix.shape[1], "Must be a square numpy array"
    
    # mask the diagonal and lower triangle and output flattened array
    flattened_out = square_matrix[np.triu_indices(len(square_matrix), k=1)] 

    return flattened_out
```

## Example usage:
```py
import numpy as np

square_matrix = np.array([[1,0,0,0],
                          [0,1,0,0],
                          [0,0,1,0],
                          [0,0,0,1]])

flattenRDM(square_matrix)
```
Recipe by [Shawn Rhoads](https://github.com/shawnrhoads)
