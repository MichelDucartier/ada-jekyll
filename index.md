---
layout: post
title: Unraveling the connections between actors and characters in movies
subtitle: Brought to you by the Advanced Data Arsonists
---

## Introduction 

In the movie industry, creativity is generally considered to be a key factor in the success of a film. Actors often need to reinvent themselves to keep audiences hooked, but do they really ? Some actors tend to develop a comfort zone and keep playing the same type of movies/characters. Our projects aims at discovering those comfort zones, when they are created and what happens when actors step out of it. Conversly, we also want to evaluate if a given role/character tends to be played only by a subset of actors and which feature(s) these actors share, which could lead us to uncover racial or gender biases in film castings. We build on top of the results of the [original paper](http://www.cs.CMU.edu/~ark/personas/) in order to identify in a more fine-grained approach if an actors exhibit a recurring persona accross the characters they play.


## Unraveling the threads of cinematic success

Is a movie's success etched in box office gold and revenue, or does it reside in the hearts of viewers and the pens of critics? While blockbusters rake in the cash, they represent just a sliver of the film universe.

<!-- ![Revenue vs Iceland](/assets/img/revenue_vs_iceland.png) -->

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/box_office_vs_gdp.html"></iframe>
</div>


By way of comparison, the annual box office of the entire film industry is equivalent to Iceland's GDP! But why are they so popular? What makes a good movie? Let's delve into what truly marks a film's success!

**The Spectrum of Ratings: A Glimpse into Popularity**
Dive into the world of ratings, you'll see it's less about the extremes and more like a cozy middle part of the road party. 

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/ratings_histogram.html"></iframe>
</div>

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/movie_votes.html"></iframe>
</div>


We can notice that from the distribution of movie ratings that fewer movies receiving very low or very high ratings, with a slight tendency of voters to rate movies positively. The "number of movies over number of votes" plot tells us that only a small number of movies receive a large number of movies.  The "more votes, more hype" graph shows that if a movie gets more eyeballs, it's likely to get more love or hate in the ratings.

What has influence over this popularity? Is it a riveting storyline, memorable characters, or the star power of actors? Our love for cinema often ties to the allure of familiar faces. Yet, our analysis uncovers a pattern — a stage where actors don familiar masks more often than not.

## Star Power: Are Actors the Puppet Masters of Popularity?

As big movie fans, we love some movies because one of our favourite actors play in them.
However, some actors stick to playing the same characters. We got really intrigued by this phenomena. Let's study each actor and the characters they play.

## Tropes : Figurative or metaphorical personas
Tropes are those tried and true clichés that we can spot a mile away. Whether it's the "over-the-top villain" with a maniacal laugh or the "quirky best friend" who's always got the one-liners, these are the bread and butter of movie land and we just can't get enough of them.

## Stereotypes on Screen: The Tropes We Love to Recognize
To find the most recurrent tropes in the movie industry, we use a Latent Dirichlet Allocation method described [here](https://aclanthology.org/P13-1035.pdf). This algorithm creates 50 personas and associates each of them with a list of words that appear frequently with those personas. Let's try look at those personas a little bit more closely! To visualize the meaning of different personas, we will use the [word2vec](https://arxiv.org/abs/1301.3781) representations of the most frequent words in a couple of generated tropes. Then, we use TSNE to reduce those high dimensional vectors to 2 dimensions in order to visualize them. Here are our results for a couple of tropes:

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/persona_scatter.html"></iframe>
</div>

We definitely find our beloved villain with persona 43! Words like "vampire", "witch" and "pirate" are associated to this persona. Switching gears, certain personas have a peculiar penchant for verbs rather than the usual character attributes, just like our friend Persona 14. Take a moment to appreciate the action-packed spectacle, where verbs like "stab," "threaten," "kill," and "kidnap" take center stage. Believe me, crossing paths with Persona 14 is like willingly stepping into a party where enemies are the uninvited guests...

This leaves us to wonder what is the proportion of actors that tend to play the same type of movies ?


We find out that there are only a few famous actors with multiple roles. Only 16% of actors had more than 5 roles.  
It turns out Hollywood's got a "type," and many actors fit right into it. The big names might be playing it safe in their cinematic comfort zone. 


-> graph

 This bifurcation raises intriguing questions: Do more roles equate to greater success, or simply greater visibility? Is the industry inclined to favor a select group and to typecast actors, or do these actors possess an adaptive chameleon-like quality that lands them role after role, or simply actors tend to have a preference to play some roles more than others.. We defined metrics that help us understand to what extent actors prefer certain types of characters, or personas, in their careers.
One key metric is the cross entropy metric, which essentially measures the predictability of an actor's persona based on their previous roles. It gives us a numerical value representing how often an actor is seen in a particular type of role. Think of it as a way to quantify an actor's range or lack whether they are frequently cast as the villain, the hero, the sidekick, and so on.
Another fascinating measure is the mutual information metric. This one goes a step further by comparing an actor's choices against the overall distribution of personas in the acting world. It captures how unique an actor's role selection is compared to the average. In other words, it can tell us whether an actor's repertoire is not particularly special or stands out from the crowd.
... 








