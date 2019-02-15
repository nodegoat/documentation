## Analysis

The Analysis functionality performs graph measures and metrics on your data selection.

You can save results to the active 'workspace' or to a stored Analysis configuration. The results can be used in [Filters](/usage/filter/README.md) and [Conditions](/usage/conditions/README.md) and subsequently all other nodegoat functionalities.

Use the [Context](/usage/analysis/README.md#context) to include results saved to stored Analysis configurations in the Analysis column in overviews.

### Graph

The Scope allows you to create edges between the source nodes (Objects in the selection of the currently active Type) and target nodes (Objects referenced by the indicated path in the Scope).

The currently available algorithms are:
* Count
* Shortest path
* nodegoat path  
  Highlight node relevance within shortest paths; calculate shortest path with a mode of betweenness centrality.
* Betweenness centrality
* Closeness centrality
* Closeness eccentricity
* Clustering coefficient
* Pagerank

When applicable to the alorithm you can indicate whether you want to use the graph's weight (weight being the total edge length between nodes based on duplicate edges):
* Weight to closeness: edges add to a shorter total edge length (lower weight).
* Weight to distance: edges add to a longer total edge length (higher weight).

### Context

By selecting stored Analysis configurations in the Analysis Context settings, it is possible configure the Analysis column to be able to directly compare and sort an Object's various graph measures and metrices.

