# pacakge: scipy

## 稀疏矩阵

```py
from scipy import sparse
from sklearn.cluster import SpectralClustering
import numpy as np
# create a 30x1000 dense matrix random matrix.
D = np.random.random((30, 1000))
# X is a "full" matrix that is intrinsically sparse.
X = D * (D < 0.10)
# convert D into a sparse matrix (type coo_matrix)
S = sparse.coo_matrix(X)
```

稀疏矩阵S是坐标和坐标对应值的键值对。