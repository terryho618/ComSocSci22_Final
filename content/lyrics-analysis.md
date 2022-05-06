---
title: Lyrics Sentiment Analysis
prev: network-analysis
next: louvain-network
---

The text that we analyzed was the taken from the lyrics we were able to tokenize.

We did sentiment analysis on these tokens using the LabMT library which is a list of words that is a given a rating for which represents a negative or positive sentiment. The lower the number is, the more negative that word is, and the higher the number is, the more positive the word is.

There were two ways we did sentiment analysis: 
1. The moving average sentiment over the song's progression
    - smooth the sentiment values to better represent the progression of the song's sentiment
2. The average over predefined buckets of the song's progression
    - Squish the progression into 100 buckets that each contain an average sentiment value
    - Each bucket will contain the sentiment of 1% of the tokens

There are two values that were calculated:
1. Positive/Negative sentiment value
2. Absolute sentiment value (represents how emotional the song is)

As an example, the graphs below represent the different sentiment analysis methods and values using Taylor Swift's top song:
![](/plots/taylor_sentiment_progression.svg)

As shown the moving average window is not large enough to encapsulate the entire song whereas the bucketed method isn't representative of the entire song. 

The mean sentiment of each song was also calculated and then adjusted to have a negative or positive value.

**Most Positive Sentimental Genres**
> - funk: 0.1772
> - urban contemporary: 0.1642
> - r&b: 0.135
> - indie soul: 0.1236
> - post-teen pop: 0.1174

**Most Negative Sentimental Genres**
> - k-pop: -0.1382
> - metalcore: -0.0872
> - underground hip hop: -0.04692
> - trap: -0.03906
> - gangster rap: -0.0372

**Some Interesting Louvain Partitions**
> - Partition 25 is the latin music partition (most emotional and positive)
> - Partition 89 is soul and funk  (second most emotional and positive)
> - Partition 10 is experimental metal (most negative)
> - Partition 53 is modern pop/social media pop (most common)

Genres were filtered out to only include genres with more than 250 songs.

<!-- update this later -->
![](/plots/sentiment_progression.svg)

The first row represents the most positive sentiment, the second row is the most emotional, and the third row is the most negative sentiment. The red line is the mean bucketed sentiment or emotion over the given genre.