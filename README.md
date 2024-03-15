# Code for TMLR 2024 Paper: Learning Sparse Graphs for Functional Regression using Graph-induced Operator-valued Kernels
This GitHub repository contains codes used for TMLR 2024 paper 'Learning Sparse Graphs for Functional Regression using Graph-induced Operator-valued Kernels.'

## Paper
[Learning Sparse Graphs for Functional Regression using Graph-induced Operator-valued Kernels (TMLR 2024)](https://openreview.net/forum?id=f9l4eiPKpV)

### Abstract
A functional regression problem aims to learn a map $\mathfrak{F}:\mathcal{Z}\mapsto\mathcal{Y}$, where $\mathcal{Z}$ is an appropriate input space and  $\mathcal{Y}$ is a space of output functions. When $\mathcal{Z}$ is also a space of functions, the learning problem is known as function-to-function regression. In this work, we consider the problem of learning a map of the form ${F}:{\mathcal{Z}}^p\mapsto\mathcal{Y}$, a many-to-one function-to-function regression problem, where the aim is to learn a suitable $F$ which maps $p$ input functions to an output function.  In order to solve this regression problem with $p$ input functions and a corresponding output function, we propose a graph-induced operator-valued kernel (OVK) obtained by imposing a graphical structure describing the inter-relationships among the $p$ input functions. When the underlying graphical structure is unknown, we propose to learn an appropriate Laplacian matrix characterizing the graphical structure, which would also aid in learning the map $F$. We formulate a learning problem using the proposed graph-induced OVK, and devise an alternating minimization framework to solve the learning problem. To learn $F$ along with meaningful and important interactions in the graphical structure, a minimax concave penalty (MCP) is used as a sparsity-inducing regularization on the Laplacian matrix. We further extend the alternating minimization framework to learn $F$, where each of the $p$ constituent input functions as well as the output function are multi-dimensional. To scale the proposed algorithm to large datasets, we design an efficient sample-based approximation algorithm. Further, we provide bounds on generalization error for the map obtained by solving the proposed learning problem. An extensive empirical evaluation on both synthetic and real data demonstrates the utility of the proposed learning framework. Our experiments show that simultaneous learning of $F$ along with sparse graphical structure helps in discovering significant relationships among the input functions, and motivates interpretability of such relationships driving the regression problem.

### Citation
To cite this work, you can use the following bibtex entry:
 ```bib
@article{saha2024learning,
title={Learning Sparse Graphs for Functional Regression using Graph-induced Operator-valued Kernels},
author={Akash Saha and Balamurugan Palaniappan},
journal={Transactions on Machine Learning Research},
issn={2835-8856},
year={2024},
url={https://openreview.net/forum?id=f9l4eiPKpV}
}

```

## About Code

### Dependencies:
    Python version: 3.7
    Packages: numpy, scipy, matplotlib, cvxopt, networkx, concurrent.futures

### File Descriptions:
The codes are divided into the following folders:
#### synthetic_data
We have three settings for synthetic data: 3 node, 12 node and 25 node experiments. Each set of experiments is further segregated into 80_20_20, 160_40_40, and 320_80_80 cases, denoting the number of samples in training, validation, and test sets. The generate_data.ipynb file contains the details of the data generation process for each setting. We have provided the codes for Sparse OpMINRES-L-D and Sparse Non-Pos-OpMINRES-L-D for every case in each setting with the best performing hyperparameters. For the 3 node 80_20_20 case, we have provided the codes for using graph-induced OVKs with $k_2$ as Epanechnikov and RBF kernels.
#### weather_data
We consider 1-minute data of Wyoming ASOS collected from [IEM ASOS One Minute Data](https://mesonet.agron.iastate.edu/request/asos/1min.phtml) (Iowa Environmental Mesonet, 2022). The data has been collected for an interval of 2 hours for both input functions and output function from January 2022 to August 2022. Data collected at one-minute intervals for 12 different weather stations in Wyoming was pre-processed to create 2-hour interval data by disregarding intervals where data was missing in any of the 12 stations. A total of 718 samples were collected after missing data was removed. A truncated trigonometric basis of $L^2([0,1])$ with 80 basis functions has been considered for encoding the functional data. We segregate the weather data experiments into small data (80/20/20) and full data (472/123/123), denoting the number of training samples/validation samples/test samples, respectively.  We have provided the codes for Sparse OpMINRES-L-D for both full and small data with the best performing hyperparameters. We also showcase the sample-based approximation algorithm with Sparse OpMINRES-L-D for full data.
#### NBA_data
The movement of basketball and 21 players involved on the court ($x-y$ coordinates) in the Atlanta Hawks (ATL) vs Utah Jazz (UTA) match on November 15, 2015 has been considered in this experiment. This data for the particular match is available in the Github repo [NBA Movement Data](https://github.com/sealneaward/nba-movement-data). The data has been collected for different plays for both input functions of 21 players and output function denoting the position of the ball, which includes missing data corresponding to some players in different plays. As plays in a basketball game are of different time duration, we use a truncated trigonometric basis of $L^2([0,1])$ with 80 basis functions to sample the functions at fixed 100 points on $[0,1]$. We provide the codes for Sparse OpMINRES-L-D incorporating an extension of OpMINRES for multi-dimensional functional regression problems with the best performing hyperparameters. We also showcase the sample-based approximation algorithm with Sparse OpMINRES-L-D for NBA data.

### Contact for any query:
    akashsaha@iitb.ac.in
    akashsaha06@gmail.com
    balamurugan.palaniappan@iitb.ac.in
