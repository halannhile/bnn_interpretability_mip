# Training Experimentally Robust and Interpretable Binarized Regression Models Using Mixed-Integer Programming 

Proving the interpretability of MIP's learned parameters for BNNs, on visual tasks (MNIST) and non-visual tasks (Flags, Ubuntu), using Continuous k-Nearest Neighbours (CkNN)

## Methodology 

* Obtain MIP's learned parameters for the weights of BNNs 
* Represent each input feature (e.g., each pixel for visual tasks like MNIST) as a vertex 
* Connect two vertices by an edge based on their Hamming distance to each other
* An edge is defined for a pair of features $x,y \in F$ if 

$$d(x,y) < \delta * \sqrt{d(x,x_k)d(y,y_k)}$$ 

where $d(x,y)$ denotes the Hamming distance between features $x$ and $y$, $\delta \in \mathbb{R}_+$ is a parameter controlling the sparsity of the graph, and features $x_k, y_k \in F$ are the k-th nearest neighbours of features $x$ and $y$ respectively

Hamming distance is chosen in this case because of its intuitive link to the set of possible weights value for BNNs, $\lbrace -1,0,1 \rbrace$. Moreover, in CkNN, the distance $d(x, y)$ must be a legitimate distance metric to ensure geometrical consistency. 


## Experimental Results 

**For MNIST:**

![image](https://user-images.githubusercontent.com/55796146/198814817-232c4b2a-5a2c-472d-9d79-767eab703c04.png)


**For Flags:**

![image](https://user-images.githubusercontent.com/55796146/198814865-699d535e-203e-40f2-b915-c35b00f2f45d.png)


**For Ubuntu:** 

![image](https://user-images.githubusercontent.com/55796146/198814669-4ec9792e-8db8-46a6-850e-7c9c43578acc.png)



## Citation
S.Tule N.H.L.Le and B.Say, "Training Experimentally Robust and Interpretable Binarized Regression Models Using Mixed-Integer Programming" *IEEE Symposium Series on Computational Intelligence*, 2022 
https://doi.org/10.48550/arXiv.2112.00434 

## Reference 

<a id="1">[1]</a> 
T.Berry and T.Sauer, "Consistent manifold representation for topological data analysis" *Foundations of Data Science*, vol.1, no. 1, pp. 1-38, 2019 
https://www.aimsciences.org/article/doi/10.3934/fods.2019001

<a id="2">[2]</a> 
Z.Liu and M.Barahona, "Graph-based data clustering via multiscale community detection" *Applied Network Science*, 3, 2020 
https://doi.org/10.1007/s41109-019-0248-7
