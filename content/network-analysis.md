---
title: Network analysis
prev: data-description
next: text-analysis
---
There are 3 networks: the Louvain Network, the Genre Network, and the Sentiment Network. 

**Louvain Network**
![](/figure/louvain_network.png)

**Genre Network**
![](/figure/genre_network.png)


As shown in the two figures above, the Louvain Graph which uses the Community Detection algorithm is much better at partitioning the communities compared to the partioning based on genres. You can also see this in the figure below which compares the two values of modularity between the two networks. The Louvain partition modularity is 0.8833 compared to the Popular Genre partition modularity which is only 0.4174.


![](/figure/modularity_difference.png)

**Sentiment Network**
![](/figure/sentiment_network.png)
![](/figure/colorbar.png)

The sentiment network is represented by nodes that are colored green, yellow, or red, meaning the sentiment of the artist is positive, neutral, or negative respectively. The node is sized by the emotion of the artist, meaning that the greater the absolute value of the sentiment, the larger the size is. This is to represent how emotional the artist's lyrics are and to see trends within the genres. For example, at the bottom left of the network, there is a green cluster with a lot of big nodes, showing that latin pop is generally positive and emotional. 