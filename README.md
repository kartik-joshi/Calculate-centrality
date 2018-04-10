# Graph-Centrality

## Calculate graph various centrality

1. Degree Centrality: 

Degree is a simple centrality measure that counts how many neighbors a node has. If the network is directed, we have two versions of the measure: in-degree is the number of in-coming links, or the number of predecessor nodes; out-degree is the number of out-going links, or the number of successor nodes. Typically, we are interested in in-degree, since in-links are given by other nodes in the network, while out-links are determined by the node itself. Degree centrality thesis reads as follows:

A node is important if it has many neighbors, or, in the directed case, if there are many other nodes that link to it, or if it links to many other nodes.

### Math

"Let $A = (a_{i,j})$ be the adjacency matrix of a directed graph. The in-degree centrality $x_{i}$ of node $i$ is given by: $$x_{i} = \sum_k a_{k,i}$$ or in matrix form ($1$ is a vector with all components equal to unity): $$x = 1 A$$ The out-degree centrality $y_{i}$ of node $i$ is given by: $$y_{i} = \sum_k a_{i,k}$$ or in matrix form: $$y = A 1$$"


2. Closeness Centrality:
Closeness centrality measures the mean distance from a vertex to other vertices. Recall that a geodesic path is a shortest path through a network between two vertices. Suppose $d_{i,j}$ is the length of a geodesic path from $i$ to $j$, meaning the number of edges along the path. Then the mean geodesic distance for vertex $i$ is:
"$\displaystyle{l_i = \frac{1}{n} \sum_j d_{i,j}}$"

3. Betweenness Centrality:
Betweenness centrality measures the extent to which a vertex lies on paths between other vertices. Vertices with high betweenness may have considerable influence within a network by virtue of their control over information passing between others. They are also the ones whose removal from the network will most disrupt communications between other vertices because they lie on the largest number of paths taken by messages.

Mathematically, let $n_{s,t}^{i}$ be the number of geodesic paths from $s$ to $t$ that pass through $i$ and let $n_{s,t}$ be the total number of geodesic paths from $s$ to $t$. Recall that a geodesic path is not necessarily unique and the geodesic paths between a pair of vertices need not be node-independent, meaning they may pass through some of the same vertices. Then the betweenness centrality of vertex $i$ is:

"$\displaystyle{b_i = \sum_{s, t} w_{s,t}^{i} = \sum_{s, t} \frac{n_{s,t}^{i}}{n_{s,t}}}$"
where by convention the ratio $w_{s,t}^{i} = 0$ if $n_{s,t} = 0$. Notice that each pair of vertex $s, t$ contribute to the sum for $i$ with a weight $w_{s,t}^{i}$ between 0 and 1 expressing the betweenness of $i$ with respect to the pair $s, t$



4. Eigenvector Centrality:
Eigenvector Centrality

A natural extension of degree centrality is eigenvector centrality. In-degree centrality awards one centrality point for every link a node receives. But not all vertices are equivalent: some are more relevant than others, and, reasonably, endorsements from important nodes count more. The eigenvector centrality thesis reads:

A node is important if it is linked to by other important nodes.
Eigenvector centrality differs from in-degree centrality: a node receiving many links does not necessarily have a high eigenvector centrality (it might be that all linkers have low or null eigenvector centrality). Moreover, a node with high eigenvector centrality is not necessarily highly linked (the node might have few but important linkers).

Eigenvector centrality, regarded as a ranking measure, is a remarkably old method. Early pioneers of this technique are Wassily W. Leontief (The Structure of American Economy, 1919-1929. Harvard University Press, 1941) and John R. Seeley (The net of reciprocal influence: A problem in treating sociometric data. The Canadian Journal of Psychology, 1949).

### Math

" Let $A = (a_{i,j})$ be the adjacency matrix of a graph. The eigenvector centrality $x_{i}$ of node $i$ is given by: $$x_i = \frac{1}{\lambda} \sum_k a_{k,i} \, x_k$$ where $\lambda \neq 0$ is a constant. In matrix form we have: $$\lambda x = x A$$ "
