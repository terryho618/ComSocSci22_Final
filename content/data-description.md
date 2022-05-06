---
title: Data description
prev: "/"
next: network-analysis
---

**Spotify**  
The dataset involves a network of artists on Spotify acquired from the Tekore API. They were first taken from several playlists and the network expanded by a depth of 3. All artists should have 20 related artists and those that do not either have corrupt metadata or are obscure and do not have enough data.
- 90,815 artists

**Everynoise.com**  
We also obtained the genre(s) related to each artist by scraping data from everynoise.com. For example, a return output could be "pop" or "pop, rock". Most genres have very few artists assigned to them.
- 4,425 unique genres
![](/plots/genre_distribution.svg)

**LyricsGenius**  
We obtained the lyrics to the most popular song of each artist according to Spotify with the LyricsGenius API. We were limited to 1 song per artist due to time constraints, and rate limit and sizing of data. Some of the songs did not contain lyrics (instrumental) or did not exist on Genius. We did not do analysis on those songs. 

We were also not able to analyze every single song due to the fact that some songs are not written in a language within the LabMT library. We were only able to obtain tokens of lyrics in the language of English, French, German, Hindi, Indonesian, Korean, Portugese, Russian, or Spanish.

Each song was on average 1600 characters:
![](/plots/lyric_lengths.svg)


**Important Properties of The Dataset**
- Always-On
    - The dataset is always-on as the data is gathered from Spotify, whose nature is always-on. Spotify updates the most popular songs of an artist and their social network based on their own algorithm.
- Algorithmically Confounded
    - The dataset is algorithmically confounded as it is not naturally occurring and is engineered by people. The problem with this is that the Spotify algorithm to find related artists and the language detection algorithm is highly invisible. The sentiment values are also compiled and found with an algorithm. 