---
title: Text analysis
prev: network-analysis
---

**Sentiment Analysis**  
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
![](/figure/taylor_swift_sentiment.png)

As shown the moving average window is not large enough to encapsulate the entire song whereas the bucketed method isn't representative of the entire song. 

The mean sentiment of each song was also calculated and then adjusted to have a negative or positive value.

The following histograms represent the sentiment progression (marked by the red line) of each genre:
 ![](/figure/genre_sentiment_progression.png)