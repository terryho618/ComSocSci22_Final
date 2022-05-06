---
title: The Spotify Network Analysis
prev: data-description
next: lyrics-analysis
---
The Spotify Network contains 90,815 nodes each representing an artist. An edge is created between the artist and their related artists. There can be multiple edges between the same two artists. Each edge is weighted by the order of the artist on the related artist page. The graph is now a single-edge graph by average parallel edge weights.

**The Spotify Artist (Genre) Network**  
Looking at the Spotify Artist Network network, each color represents a different genre. Some artists have multiple genres, therefore, only the most representative genre of the artist is used, i.e. the biggest genre based on total song count.
![](/figure/genre_network.png)
(This is a down-scaled version. In order to see this graph in better quality please click **[this](/genre-network)**)

The Spotify Artist Network is a representation of genres on Spotify. Artists are spread across the canvas and are then positioned based on how related to other artists they are. In simple terms: related artists attract, unrelated artists repel. Each artist on the canvas will have 20 other related artists based on their monthly listener overlap, their popularity, their general genre and which playlists they both appear on. 

For this type of social network, with a constant branching factor, the network gets more and more dense and grows exponentially as a result. Therefore, since this network is only based on three iterations of related artists, many artists are missing and so this graph is only a snippet of the real network. Notice how the genres on the borders are much more contiguous and dense, this might be because these genres are not yet explored at the third iteration. 

Although, the genres in the middle are more scattered, some bigger genres still appear contiguous and large. For example, on left-middle side there is a big green community, which is the "EDM" genre community. This genre seems way more contiguous or dense than the genres in the middle of the graph. Another reason for this might be that all pop genres are placed in the middle and so this part of the social network is ever evolving and, therefore, it is hard to pinpoint exact genres for these types of artists - which may be why Everynoise.com sometimes just simply deems an artist as "pop". Some genres are also a lot more fragmented due to sub-genres, such as "indie rock" and "indie pop" which are both sub-genres of "rock" and "pop".

**The Spotify Artist (Louvain) Network**  
For the Louvain network, the Louvain community detection algorithm is used to detect communities within the network. In the Louvain network, artists are only assigned one community.

The detection algorithm uses modularity, a measure of the amount of information that is shared by the communities, to determine the communities. Non-weighted modularity is the fraction of the number of edges linking members in the same community minus the fraction of edges in a randomly distrubted network. This measure upweighs partitions that are denser than expected from the random network. The weighted modularity means that the larger edge weights are have more emphasis on the modularity. Two artists which are more related are more likely to be in the same community using this algorithm.

![](/figure/louvain_network.png)
(This is a down-scaled version. In order to see this graph in better quality please click **[this](/louvain-network)**)

As shown in the two figures above, the Louvain Graph which uses the Community Detection algorithm is much better at partitioning the communities compared to the partioning based on genres. The Louvain partition modularity is 0.8823 compared to the Popular Genre partition modularity which is only 0.4161. The number of Louvain communities is 95 where the number of Genre communities is 3,260. This is because the Genre network is very fragmented due to the number of smaller artists and genres.

The much-fragmented pop community in the middle of the graph seems to be detected by the Louvain algorithm and simply merged to a single contiguous cluster instead. This cluster consists of 5.89% alt z, 5.67% indie electropop and 4.6% pop which are the largest parts of this community. As such, it is safe to say that this community encompasses many tiny fragmented genres at once.

In order to determine if these modularities are significant from a random network, 1000 random networks are created based on the same graph for both the Louvain and Genre partition.

The results are displayed in this plot:
![](/plots/modularity_distributions.svg)

The random networks are typically less dense in communities compared to the original network. Due to the large number of edges compared to nodes, the modularity is also generally much lower in the random networks.