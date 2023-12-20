---
layout: post
title: The love-hate relationship between actors and their characters
subtitle: Brought to you by the Advanced Data Arsonists
---

## Introduction 

Movies, they're not just projections on a wall, they're emotional odysseys. Each scene is carefully planned; every line
is ingeniously written. The film industry isn't merely a storyteller, it's a maestro of the grand symphony of creativity
and tradition, innovation and nostalgia.

Perched on the shoulders of the [original publication](http://www.cs.CMU.edu/~ark/personas/), we're taking a deep dive
into cinematic personas. With a more nuanced lens, we're out to uncover if actors wear their characters like well-fitted
gloves, repeatedly slipping into familiar roles, or if they're chameleons, constantly changing hues.

Our quest starts with the tales within the CMU Movie Summary Corpus — more than 42,000 narratives waiting to spill their
secrets. We're exploring deeper, armed with IMDb's vast archives and WikiData' rich knowledge base, to bring new 
dimensions to the personas we explore.

We're on a mission to spot actors that created comfort zones for themselves, our magnifying glass being our data analysis
knowledge. Throughout this analysis, we will be zooming in on patterns, crunching numbers, and charting plots to uncover
comfort zones in movie genres and in personas. We'll also take a peek behind the casting curtain to try and find hidden
patterns in who gets to play the hero, the villain, the casanova?

Join us on this exclusive backstage pass as we lift the velvet curtains on this data. Together, we'll navigate through
this lattice of information to perhaps capture the essence of cinema typecasting.

## The CMU Movie.. what ?
The CMU Movie Summary Corpus is a rich corpus which contains multiple datasets related to movies, the characters in it, 
corresponding actors and many other miscellaneous features spanning on more than a hundred year of productions from the
movie industry. The [original publication](http://www.cs.CMU.edu/~ark/personas/) mentioned above used movie summaries
with Latent Dirichlet Allocation to skillfully extract 100 personas and the distribution of personas for each character.
This distribution is what we will use in our analysis further down.

We will also focus on genre-based comfort zones, that is, actors that show recurrent patterns in the genres on movies
they play in. We can visualize the genre distribution of movies in the pie chart below.

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/genre_pie.html"></iframe>
</div>

Something interesting emerging here is that movie genres are not very polarized. We do not have a couple of overwhelmingly
big fractions of one type of movies and breadcrumbs around it.
# LUCA STOP HERE

## How successful is the movie industry?

But first we need to ask ourselves how big is this success? Is the movie industry as lucrative as we think? Or is it some petty money that does not deserve our attention... To get a more intuitive feel about the magnitude of the money involved, we need to compare the movies' revenue to something tangible such as a country's GDP for instance!

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/box_office_vs_gdp.html"></iframe>
</div>


By way of comparison, the annual box office of the entire film industry is equivalent to Iceland's GDP! Keep in mind that this plot only takes into account the *box-office* revenue of the film industry. Other sources of revenues such as streaming platform or DVDs are not even counted in this plot! But why are they so popular? What makes a good movie? Let's delve into what truly marks a film's success!

## Unraveling the threads of cinematic success

Meet our new friend Bob! Bob is a newcomer in the movie acting world. He has always been a fan of sci-fi movies like Star Wars! His favourite character is Darth Vader because he really enjoys playing the bad guy. However, Bob is not a fool, he knows that the industry is ruthless. One mistake and your career is over! He is really worried that he can not play the same character over and over again as he will become too predictable. On the other hand, he also fears falling into the other extreme, i.e. playing several different types of role without forging a clear identity. What should he do? Well, let's help him with some data analysis!

**The Spectrum of Ratings: A Glimpse into Popularity**

Bob really wants to maximise the income from the films he plays in. Unfortunately, only a handful of films are able to make it to the box office. Indeed, in our dataset almost 90% of movies does not have a box-office revenue! Bob is still a newcomer to this industry and can not play in those big blockbusters yet. Nonetheless, he remembers why he wanted to become an actor in the first place. Even though money is important, Bob has always wanted to move people's hearts! 

Therefore, let's have a look at the movies' rating. In our analysis, we choose the IMDb database. As we'll see, it's less about the extremes and more like a cozy middle part of the road party. 

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/ratings_histogram.html"></iframe>
</div>

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/movie_votes.html"></iframe>
</div>

We can notice from the distribution of movie ratings that fewer movies receiving very low or very high ratings, with a slight tendency of voters to rate movies positively. The "number of movies over number of votes" plot tells us that only a small number of movies receive a large number of votes.

What has influence over this popularity? Is it a memorable characters, or the star power of actors? Should Bob play the same type of character over and over again to create a sense of comfort in the public, or does he need to keep reinventing himself to surprise the audience?
To uncover the best strategy for Bob, he needs to know what sort of roles he needs to play. Can he stick to play those menacing villains like Darth Vader during his whole career? But before we answer this question, we need to know what defines a "villain". Not in the philosophical sense but as a cliché! In other words, we need to extract the different tropes from our movies.

<!-- 
**Roles as a measure of actors' ability to reinvent themselves?**

It could be tempting

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/actor_roles.html"></iframe>
</div>

We find out that there are only a few famous actors with multiple roles. Only 16% of actors had more than 5 roles.  
It turns out Hollywood's got a "type," and many actors fit right into it. The big names might be playing it safe in their cinematic comfort zone.  -->


### Tropes : Figurative or metaphorical personas

Tropes are those tried and true clichés that we can spot a mile away. Whether it's the "over-the-top villain" with a maniacal laugh or the "quirky best friend" who's always got the one-liners, these are the bread and butter of movie land and we just can't get enough of them.

### Stereotypes on Screen: The Tropes We Love to Recognize

To find the most recurrent tropes in the movie industry, we use a Latent Dirichlet Allocation method described [here](https://aclanthology.org/P13-1035.pdf). This algorithm creates 50 personas and associates each of them with a list of words that appear frequently with those personas. Let's try look at those personas a little bit more closely! Every actor's role are associated with a vector of 50 components. Each component $i$ represent the "porportion" of persona $i$ represented in the given role. To visualize the meaning of different personas, we will use the [word2vec](https://arxiv.org/abs/1301.3781) representations of the most frequent words in a couple of generated tropes. Then, we use TSNE to reduce those high dimensional vectors to 2 dimensions in order to visualize them. Here are our results for a couple of tropes:

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/persona_scatter.html"></iframe>
</div>

We definitely find our beloved villain with persona 43! Words like "vampire", "witch" and "pirate" are associated to this persona. Switching gears, certain personas have a peculiar penchant for verbs rather than the usual character attributes, just like our friend Persona 14. Take a moment to appreciate the action-packed spectacle, where verbs like "stab," "threaten," "kill," and "kidnap" take center stage. Believe me, crossing paths with Persona 14 is like willingly stepping into a party where enemies are the uninvited guests...

### A measure of an actor's preference relatively to the music industry

This bifurcation raises intriguing questions: Do more tropes equate to greater success, or simply greater visibility? Is the industry inclined to favor a selected group and to typecast actors, or do these actors possess an adaptive chameleon-like quality that lands them role after role, or simply actors tend to have a preference to play some roles more than others.. We defined metrics that help us understand to what extent actors prefer certain types of characters, or personas, in their careers.

Conceptually, let's imagine that Alice takes a random role in our dataset and among the different personas that make up this role, she chooses one persona randomly with probabilities proportional to the proportion of the persona for this role (i.e if a role is 50% "bad guy" and 50% "big muscled guy", then Alice has 50% of chance to choose the "bad guy" persona and likewise for the "big muscled guy"). Our best shot to guess which persona she took would be to take the most represented persona:

<div class="row">
  <div class="small-column">
    <span class="helper"></span> <img src="assets/img/default_portrait.png" class="portrait-img" alt="DefaultPortrait" style="width:100% ">
  </div>
  <div class="big-column">
    <iframe class="fixed-iframe" src="assets/plot/persona_global.html" ></iframe>  
  </div>
</div>

In our case, this would be the persona 50. The 5 most important verbs for this persona are: "put", "read", "drive", "stay" and "feel". We get the impression that we're dealing with a character with no personality, a generic character who is only there to fill the void on the screen. But now, let's suppose that I tell you that Christopher Lee (the one who played Count Dooku, one of Bob's favourite characters) is the one who played this role!

<div class="row">
  <div class="small-column">
    <span class="helper"></span> <img src="assets/img/christopher_lee.png" class="portrait-img" alt="ChristopherLee" style="width:100% ">
  </div>
  <div class="big-column">
    <iframe class="fixed-iframe" src="assets/plot/christopher_lee_persona.html" ></iframe>  
  </div>
</div>


Now our answer would be different because **we gained information about the mystery persona**. Indeed, Christopher Lee tends to always play the same persona: the bad guy! He is Count Dooku, Saruman, Dracula, ... If we look at the most represented personas for Christopher Lee, we see that Persona 36 and 34 are much more represented than the other ones. Here are the top verbs for both personas:
- Persona 36: "go", "turn", "put", "throw", "reveal", "keep"
- Persona 34: "recognize", "arrange", "place", "set", "invite", "threaten"

Persona 36 seems to be a generic persona without too much obvious structure. However, persona 34 is much more interesting. Words like "threaten", "arrange", "place", "set" and "invite" suggest that this persona captures some sort of manipulative villain which is very fitting for an actor like Christopher Lee!

In this case, we gained a lot of information about the "mystery persona" **because Christopher Lee's roles revolve around a couple of tropes**. In the other extreme, if an actor tends to play personas that are very uniform, then we would actually lose information about this "mystery persona"


### Mutual Information Preference score of personas: 

With this key idea of information gain we design our first key metric: the **mutual information preference metric, MIP**. 
The MIP score for each trope distribution reveals how closely an actor's choices align with, or diverge from, the collective narrative palette. An actor whose range of personas closely matches the global distribution would have an MIP score approaching zero, suggesting a versatile adaptability to the myriad roles the industry offers. In contrast, actors with higher MIP scores tend to have a more specialized or distinctive selection of character tropes, indicating a niche or a strong association with particular kinds of roles.
In other words, MIP can tell us whether an actor's repertoire is not particularly special or stands out from the crowd.

1. A MIP score of 1 signifies an actor with a singular focus
2. An MIP score of 0 indicates an actor whose choices mirror the global distribution of roles or genres.
3. An MIP score below 0 is where things get even more interesting. Here we find actors who are the very embodiment of diversity, their choices more varied than the industry average.

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/mip_personas.html"></iframe>
</div>


The histogram is bell-shaped with a substantial spread but with a skewness towards higher MIP scores. This distribution indicates that while there's a strong central tendency — most actors have an average degree of persona specialization.
The thicker right tail suggests that there are more actors than expected who tend to play similar types of characters consistently, as opposed to having a broader range. These are likely actors who have found a niche or are frequently typecast. The thinner left side, shows fewer actors who are characterized by a wide variety of roles, the industry's versatile figures and chameleons, leaping from role to role.

The plot highlights the extremes: We have a lot more actors with high MIP scores, often stepping into an electic array or roles and tend to be more predictable in their role choices. The right spike presents us the specialists that have found their niche. We naturally ask: Do these specialization trends observed in persona choices also mirror the genres that actors are drawn to?


### Mutual Information Preference score of genres

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/mip_genre.html"></iframe>
</div>

Turning our lens to the realm of genres, the visualization before us, a distribution of actors with respect to the Mutual Information Precision (MIP) score of genres—offers a quantified glimpse into this interplay between actors and the genres they navigate.
MIP metric, when applied to genres, tells a story about an actor's alignment with the industry's genre landscape. (add global genre distribution)
The peak around the zero mark suggests a majority of actors whose genre affiliations are in harmony with industry trends. To the **left**, where the MIP scores dip into the negatives, are the actors whose genre choices are less predictable, those who defy easy categorization. 
To the **right**, the graph thins out, representing those few actors whose careers are tightly intertwined with specific genres. These could be the icons of their domains—actors who, when we think of a thriller or a sci-fi epic, come readily to mind.

This distribution of actors across genres raises questions about the forces that shape an actor's career trajectory. Is it personal inclination, the allure of certain types of stories that resonates with their own artistic voice? Or does it reflect the typecasting tendencies of an industry that finds a formula and sticks to it, sometimes to the detriment of creative diversity?

<!-- These are the risk-takers or perhaps those who are not so easily embraced by the mainstream, their filmographies a patchwork of various styles and narratives.
-->

### Plot that michael did


### Somthing else
<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/log_likelihood_tropes.html"></iframe>
</div>
