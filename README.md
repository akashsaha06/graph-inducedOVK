# Code for TMLR 2024 Paper: Learning Sparse Graphs for Functional Regression using Graph-induced Operator-valued Kernels
This GitHub repository contains codes used for TMLR 2024 paper 'Learning Sparse Graphs for Functional Regression using Graph-induced Operator-valued Kernels.'

## Paper
[Learning Sparse Graphs for Functional Regression using Graph-induced Operator-valued Kernels (TMLR 2024)]()

### Abstract
  A functional regression problem aims to learn a map $\mathfrak{F}:\mathcal{Z}\mapsto\mathcal{Y}$, where $\mathcal{Z}$ is an appropriate input space and  $\mathcal{Y}$ is a space of output functions. When $\mathcal{Z}$ is also a space of functions, the learning problem is known as function-to-function regression. In this work, we consider the problem of learning a map of the form ${F}:{\mathcal{Z}}^p\mapsto\mathcal{Y}$, a many-to-one function-to-function regression problem, where the aim is to learn a suitable $F$ which maps $p$ input functions to an output function.  In order to solve this regression problem with $p$ input functions and a corresponding output function, we propose a graph-induced operator-valued kernel (OVK) obtained by imposing a graphical structure describing the inter-relationships among the $p$ input functions. When the underlying graphical structure is unknown, we propose to learn an appropriate Laplacian matrix characterizing the graphical structure, which would also aid in learning the map $F$. We formulate a learning problem using the proposed graph-induced OVK, and devise an alternating minimization framework to solve the learning problem. To learn $F$ along with meaningful and important interactions in the graphical structure, a minimax concave penalty (MCP) is used as a sparsity-inducing regularization on the Laplacian matrix. We further extend the alternating minimization framework to learn $F$, where each of the $p$ constituent input functions as well as the output function are multi-dimensional. To scale the proposed algorithm to large datasets, we design an efficient sample-based approximation algorithm. Further, we provide bounds on generalization error for the map obtained by solving the proposed learning problem. An extensive empirical evaluation on both synthetic and real data demonstrates the utility of the proposed learning framework. Our experiments show that simultaneous learning of $F$ along with sparse graphical structure helps in discovering significant relationships among the input functions, and motivates interpretability of such relationships driving the regression problem.

%### Citation
%To cite this work, you can use the following bibtex entry:
% ```bib
%@inproceedings{NEURIPS2020_9f319422,
% author = {Saha, Akash and Palaniappan, Balamurugan},
% booktitle = {Advances in Neural Information Processing Systems},
% editor = {H. Larochelle and M. Ranzato and R. Hadsell and M.F. Balcan and H. Lin},
% pages = {13856--13866},
% publisher = {Curran Associates, Inc.},
% title = {Learning with Operator-valued Kernels in Reproducing Kernel Krein Spaces},
% url = {https://proceedings.neurips.cc/paper/2020/file/9f319422ca17b1082ea49820353f14ab-Paper.pdf},
% volume = {33},
% year = {2020}
%}
%
%```

## About Code

### Dependencies:
    Python version: 3.7
    Packages: numpy, scipy, matplotlib

### Contact for any query:
    akashsaha@iitb.ac.in
