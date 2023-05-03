# Gower-distance

## What is Gower’s distance?

Suppose we have two observations $x_i = (x_{i1}, \dots, x_{ip})$ and $x_j = (x_{j1}, \dots, x_{jp})$, and we want a measure of how similar (or dissimilar) they are to each other. If each of the entries in these two vectors are quantitative (e.g., continuous variables), then we can use distance measures as a dissimilarity measure (e.g. Euclidean distance, Manhattan distance). How do we measure dissimilarity if instead of all numbers being numeric, some of them are binary/catagorical?

In this situation one can implement and generalised idea of similarity matrix know as Gower's distance. For each feature $k = 1, \dots, p$, we define a score $s_{ijk} \in [0,1]$. If $x_i$ and $x_j$ are close to each other along feature $k$, then the score $s_{ijk}$ is close to $1$. Conversely, if they are far apart along feature $k$ the score $s_{ijk}$ is close to $0$.

Finally, a linear combination using user-specified weights (most simply an average) is calculated to create the distance matrix.

The metrics used for each data type are as following:

Quantitative (interval) variables range-normalized Manhattan distance
Ordinal variables: variable is first ranked, then Manhattan distance is used with a special adjustment for ties
Nominal: variables of k categories are first converted into k binary columns and then the Dice coefficient is used

Advantage of this method is it is intuitive to understand and pretty straightforward to calculate.However, this method is sensitive to non-normality and outliers present in continuous variables and hence, appropriate transformations as a pre-processing step might be necessary. Besides, it can be computationally intensive for large samples as itrequires an NxN distance matrix to be calculated.







##References: Gower, J. C. (1971), “A general coefficient of similarity and some of its properties”. Biometrics, 27, 623–637.




