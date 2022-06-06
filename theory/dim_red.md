# Dimensionality Reduction
From adaptive control processes of Bellman: In absence of simplyfing assumptions, the sample size required to estimate a function of several variables to a given degree of accuracy (i.e. to get a reasonably low variance estimate) grows exponentially with the increasing number of variables.

-> THE EMPTY SPACE PHENOMENON: high dimensional spaces are inherently sparse.

Considering a sphere and a cube it is interesting to notice that for increasing D, the volume of the cube concentrates more in its cornerns and less in the inscribed sphere. 

Another example is the (hyper)-spherical shells. Virtually, al the content of a D dimensional sphere concentrates on its surface, which is only a (D-1) dimensional manifold. 

Normal distributions, the probability mass of a multivariate gaussian rapidly migrates into the trails, as the dimension increases.

Dealing with high dimension can thus intruce high fluctaution. 

CONCENTRATION OF NORMS:

Let $x = [x_{1}, ..., x_{D}] \in R^D $ be a random vector whose components $x_{k}, 1 <= k <= D$, are independent and identically distributed with a finite eight order moment. Let $\mu = E{x_{k}}$ be the common mean of all components $x_{k}$, and $\mu_{j} = E((x_{k}-\mu)^j)$ ne their common central $j^{th}$ moment. Then the mean $\mu_{|x|}$ and the variance $\sigma_{|x|}^2$ of the Euclidena norm are:

$\mu_{|x|} = \sqrt{aD -b} + O(D^{-1})$
$\sigma_{|x|}^2 = b + O(D^{-1/2})$

Variance grows linearly -> random vectors are nearly normalized. 

If you pick up a set of random vectors in d dimension all random vectors are close to the surface of a sphere of radius r. -> Euclidean distance between any two vectors is approximately constant. 

INTRINSIC/EXTRINSIC DIM 

The points of high dimensional data usually reside on a much low-dimensional manifold
$ X = {x_{\alpha}}_{\alpha \in A}, x_{\alpha} \in M, dim(M) = S$
D extrinsic dimension of X, s intrinsic dimension of X
X sample set of random vectors X in dimension D
there exist a random vector Y in dim s and an invertible anlytic function such that $f(Y) = X$

Due to the low intrinsic dimension of data, we can reduce the extrinsic dimension wihtout losing much information for many types of real-life high dimensional data, avoiding many of the curses of dimensionality. 
DR is finding a parametrization of the manifold which the points of data reside on. 

INTRINSIC DIM EXTIMATE

A finite data set can be embedded in a manyfolds of various dimension depending on the geometric structures defined on the data. E.g. by unisolvence theorem, the dataset here on the plane can be embedded in a regular curve. 

LINEAR CASE 
simplest manifold: linear subspace -> hyperplane. Among all hyperplanes S including the dataset X, choose the one with lowest dimension s. There exists a linear transformation $T : R^s -> S$. 
-> $x = T(y) = U_y + x_0$
where U is orhognal and $X_0$ is then earest point on S to the origin. 
The inverse of T provides a s-dim paramtetrisation of X.
$Y = {y \in R^S: y = T^{-1}(x), x \in X}$
wlog $x_0 = 0$ and if $U = [u_1, ..., u_s]$ then  $ {u_1,..,u_s}$ is an orthonormal basis of S. 
Distances are preserved and we have an exmaple of linear dr. 

NON LINEAR CASE

PROBLEM: if the underlying geometry is non linear, the previous approach does not give a true dimension. We then use the topological manyfold theory. 
If a manifold M in $R^D$ has dimesnion $s<D$, then the neighbourhood of each point of M is isomorrphic to $R^s$, there is an invertible differentiable map from M to $R^s$ whose inverse if differentiable.

Given a space S, the open covering of X in S is a collection of O of open sets in S whose union contains X. 
A refiniment of O is another covering O' such that each set in O' is a subset of some set in O.
An S-dimensional set X can be covered by open spheres such that each point belongs to at most s+1 open spheres. 
A subset X of a topological space S is said to have topological dimension s if every covering O of X has a refinement O' such that every point of X is covered by at most s+1 open sets in O' and s is the smallest among such integers.

-> DR methods
In most dimensionality reduction problems, the output data is not required to have the intrinsic output dimension s but a target dimension d that is lower than the intrinsic one, d<s. 

* Linear: output data are a projection of the original data (PCA MDS)
* Non-Linear: output dtaa are the manifold coordinate representation of the original data (UMAP t-SNE isomap)
# linear case 

# non linear case