---
title: Word Clouds of Most Relevant Words
prev: sentiment-network
---

To further explore the general sentiment and emotion of genres, we will now look at different word clouds based on ranking of the most relevant lyrics.

The weight scheme is based on BM25 Okapi which is a modified version of the TF-IDF scheme. Put simply, it assigns a weight to each word in a song based on how frequent it is (relevance) and how unique it is (rarity), and then it multiplies these two together. What you get are tokens which are both frequent but also unique to this certain genre only.

Below are the word clouds based on the dataset's lyrics of the biggest genres (based on song count):
![](/plots/pop_wc.svg)
![](/plots/electro_house_wc.svg)
![](/plots/dance_pop_wc.svg)
![](/plots/edm_wc.svg)
![](/plots/indie_pop_wc.svg)
![](/plots/hip_hop_wc.svg)
![](/plots/rock_wc.svg)
![](/plots/pop_rap_wc.svg)
![](/plots/electropop_wc.svg)
![](/plots/modern_rock_wc.svg)

First of all, there are two very similar genres: dance pop and pop. These word clouds are quite similar with "baby" being the highest ranking word together with "love", making the overall sentiment/mood for this genre very positive. Many pop songs are also considered "love songs" which might be a reason for this. Although pop is an ever-changing genre, love will always be a relevant thing to sing about.

Indie pop and electropop are a bit of a variation of the pop/dance pop genres. Here "baby" is not even present and the top words are based more on feelings with words such as "want", "feel" and "like" which is very emotional.

Then there are EDM and electro house. Generally, electro house is considered to be a sub-genre to EDM. Both of genres has a high weight on "night" which is unique to these two genres. While they share the mutual "yeah" with dance pop. These are generally less emotional than the pop/dance pop genres.

Even though rock and modern rock are similar, they differ very much in the most important ranked words. Both, however, have high relevance of the word "take" which creates a dichotomy with the word "love", both having opposite sentiments.

Finally, there are two genres which are not like the others. The genres hip hop and pop rap. These two genres contain vulgar language that has very negative connotations and as such have really negative sentiments. 