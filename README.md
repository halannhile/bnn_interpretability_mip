# Training Experimentally Robust and Interpretable Binarized Regression Models Using Mixed-Integer Programming 

Proving the interpretability of MIP's learned parameters for BNNs, on visual tasks (MNIST) and non-visual tasks (Flags, Ubuntu), using Continuous k-Nearest Neighbours (CkNN)

![image](https://user-images.githubusercontent.com/55796146/198813266-781a7a9f-3e80-42e7-8281-e831a6570eae.png)

## Methodology 

* Obtain MIP's learned parameters for the weights of BNNs 
* Represent each input feature (e.g., each pixel for visual tasks like MNIST) as a vertex 
* Connect two vertices by an edge based on their Hamming distance to each other
* An edge is defined for a pair of features $x,y \in F$ if 

$$d(x,y) < \delta * \sqrt{d(x,x_k)d(y,y_k)}$$ 

where $d(x,y)$ denotes the Hamming distance between features $x$ and $y$, $\delta \in \mathbb{R}_+$ is a parameter controlling the sparsity of the graph, and features $x_k, y_k \in F$ are the k-th nearest neighbours of features $x$ and $y$ respectively

Hamming distance is chosen in this case because of its intuitive link to the set of possible weights value for BNNs, $\lbrace -1,0,1 \rbrace$. Moreover, in CkNN, the distance $d(x, y)$ must be a legitimate distance metric to ensure geometrical consistency. 

## Experimental Results 

## Citation

## Reference 

<a id="1">[1]</a> 
T.Berry and T.Sauer, "Consistent manifold representation for topological data analysis"
*Foundations of Data Science*, vol.1, no. 1, pp. 1-38, 2019 
https://www.aimsciences.org/article/doi/10.3934/fods.2019001

<a id="2">[2]</a> 
Z.Liu and M.Barahona, "Graph-based data clustering via multiscale community detection"
*Applied Network Science*, 2020 
https://doi.org/10.1007/s41109-019-0248-7
