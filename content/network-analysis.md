---
title: The Spotify Network Analysis
prev: data-description
next: lyrics-analysis
---
The Spotify Network contains 90,815 nodes each representing an artist. An edge is created between the artist and their related artists. There can be multiple edges between the same two artists. Each edge is weighted by the order of the artist on the related artist page. The graph is now a single-edge graph by average parallel edge weights.

**Genre Network**  
Looking at the Genre network, each color represents a different genre. To avoid duplicate artists as some artists have multiple genres, only the most representative genre of the artist is used.
![](/figure/genre_network.png)
(In order to see this graph in better quality please click **[this](/genre-network)**)

**Louvain Network**  
For the Louvain network, the Louvain community detection algorithm is used to detect communities within the network. This is different from the Genre network as artists in this network can have multiple genres. 

The detection algorithm uses modularity, a measure of the amount of information that is shared by the communities, to determine the communities. Non-weighted modularity is the fraction of the number of edges linking members in the same community minus the fraction of edges in a randomly distrubted network. This measure upweighs partitions that are denser than expected from the random network. The weighted modularity means that the larger edge weights are have more emphasis on the modularity.
![](/figure/louvain_network.png)
(In order to see this graph in better quality please click **[this](/louvain-network)**)

As shown in the two figures above, the Louvain Graph which uses the Community Detection algorithm is much better at partitioning the communities compared to the partioning based on genres. The Louvain partition modularity is 0.8823 compared to the Popular Genre partition modularity which is only 0.4161. The number of Louvain communities is 95 where the number of Genre communities is 3,260. This is because the Genre network is very fragmented due to the number of smaller artists and genres.

In order to determine if these modularities are significant, 1000 random networks are created based on the same graph for both the Louvain and Genre partition.

The results are displayed in this plot:
![](/plots/modularity_distributions.svg)

The random networks are typically less dense in communities compared to the original network.