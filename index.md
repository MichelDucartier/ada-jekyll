---
layout: post
title: Unraveling the connections between actors and characters in movies
subtitle: Brought to you by the Advanced Data Arsonists
---

## Introduction 

In the movie industry, creativity is generally considered to be a key factor in the success of a film. Actors often need to reinvent themselves to keep audiences hooked, but do they really ? Some actors tend to develop a comfort zone and keep playing the same type of movies/characters. Our projects aims at discovering those comfort zones, when they are created and what happens when actors step out of it. Conversly, we also want to evaluate if a given role/character tends to be played only by a subset of actors and which feature(s) these actors share, which could lead us to uncover racial or gender biases in film castings. We build on top of the results of the [original paper](http://www.cs.CMU.edu/~ark/personas/) in order to identify in a more fine-grained approach if an actors exhibit a recurring persona accross the characters they play.


## Unraveling the threads of cinematic success

Is a movie's success etched in box office gold and revenue, or does it reside in the hearts of viewers and the pens of critics? While blockbusters rake in the cash, they represent just a sliver of the film universe. Let's delve into what truly marks a film's success.
(some plot to show smthg about revenue and blockbusters)

**The Spectrum of Ratings: A Glimpse into Popularity**
Dive into the world of ratings, you'll see it's less about the extremes and more like a cozy middle part of the road party. 

[movie_ratings](ada-jekyll/assets/img/movie_ratings.png)

[votes](ada-jekyll/assets/img/votes.png)

- [ ] make the graphs visiually appealing, with some lines shwoing the normal distribution, or make a distinction between the high, average, low ratings


(we can notice that from the distribution of movie ratings that fewer movies receiving very low or very high ratings, with a slight tendency of voters to rate movies positively). The "number of movies over number of votes" plot tells us that only a small number of movies receive a large number of movies.  The "more votes, more hype" graph shows that if a movie gets more eyeballs, it's likely to get more love or hate in the ratings.

What has influence over this popularity? Is it a riveting storyline, memorable characters, or the star power of actors? Our love for cinema often ties to the allure of familiar faces. Yet, our analysis uncovers a pattern — a stage where actors don familiar masks more often than not.

## Star Power: Are Actors the Puppet Masters of Popularity?

As big movie fans, we love some movies because one of our favourite actors play in them.
However, some actors stick to playing the same characters. We got really intrigued by this phenomena. Let's study each actor and the characters they play.

## Tropes ?:  define movie tropes  in a fun way 
Tropes are those tried and true clichés that we can spot a mile away. Whether it's the "over-the-top villain" with a maniacal laugh or the "quirky best friend" who's always got the one-liners, these are the bread and butter of movie land and we just can't get enough of them.

[Histogram of number of roles per actor](ada-jekyll/assets/img/roles_per_actor.png)
We find out that there are only a few famous actors with multiple personas. That means actors actually tend to play similar characters more than we expected, it is like their comfort zones or possible typecasting:where actors are repeatedly cast for similar roles in simply actors tend to have a preference to play some roles more than others. This preference we define it as the cross entropy based metric that represents the "distribution" of the preference.Mutual information gain?

- [ ]  draw conclusion from this! or graph or smthg.

It turns out Hollywood's got a "type," and many actors fit right into it. The big names might be playing it safe in their cinematic comfort zone. 

## Stereotypes on Screen: The Tropes We Love to Recognize


Our dataset containes  "crazy jealous guy", "jerk jock", "dumb blonde" ...

- [ ] maybe a network graph of these frequent tropes? 
