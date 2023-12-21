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

## So many actors.. is the movie industry really that big ?
Yes.. yes it is! The movie industry is very lucrative. To get a more intuitive feel about the amount of the money involved,
let's compare the movies' revenue to something tangible such as a country's GDP for instance.

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/box_office_vs_gdp.html"></iframe>
</div>

The annual box office of the entire film industry is roughly equivalent to Iceland's GDP! Keep in mind that this plot
only takes into account the *box-office* revenue of the film industry. Other sources of revenues such as streaming platform
or DVDs are not even counted in this plot. No wonder actors become so popular. Let's dive in, can actors make or break a movie?

## But first, the CMU Movie.. what ?
The CMU Movie Summary Corpus is a rich corpus which contains multiple datasets related to movies, the characters in it, 
corresponding actors and many other miscellaneous features spanning on more than a hundred year of productions from the
movie industry. The [original publication](http://www.cs.CMU.edu/~ark/personas/) mentioned above used movie summaries
with Latent Dirichlet Allocation to skillfully extract 50 personas and the distribution of personas for each character.
This distribution is what we will use in our analysis further down.

### A dive into personas
But what are personas exactly ? Personas, also called character tropes are those tried and true clichés that we can spot
a mile away. Whether it's the "over-the-top villain" with a maniacal laugh or the "quirky best friend" who's always got
the one-liners, these are the bread and butter of movie land and we just can't get enough of them. So personas are role
or character archetypes. To get a more intuivtive feel of what they are exactly, we've run the original publication
processing pipeline to extract the latent topics of different personas. These latent topics are linked to a list of the
most frequent words that occur in them. Then, using Word2Vec and a dimensionality reduction algorithm (t-SNE) allows us to
reduce those high dimensional vectors to 2 dimensions and visualize them. Here are a couple of character tropes visualized:

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/persona_scatter.html"></iframe>
</div>

We definitely find our beloved villain with persona 43! Words like "vampire", "witch" and "pirate" are associated to this
persona. Switching gears, certain personas have a peculiar penchant for verbs rather than the usual character attributes,
just like our friend Persona 14. Take a moment to appreciate the action-packed spectacle, where verbs like "stab",
"threaten," "kill," and "kidnap" take center stage. Believe me, crossing paths with Persona 14 is like willingly stepping
into a party where enemies are the uninvited guests...

### Don't worry, we didn't forget about your favourite action movie star

We also focus on genre-based comfort zones, that is, actors that show recurrent patterns in the genres on movies
they play in. We can visualize the genre distribution of movies in the pie chart below.

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/genre_pie.html"></iframe>
</div>

Something interesting emerging here is that movie genres are not very polarized. We do not have a couple of overwhelmingly
big fractions of one type of movies and breadcrumbs around them.

## Unraveling the threads of cinematic success

Meet our new friend Bob! Bob is a newcomer in the movie acting world. He has always been a fan of sci-fi movies like
Star Wars! His favourite character is Darth Vader because he really enjoys playing the bad guy. However, Bob is not a
fool, he knows that the industry is ruthless. One mistake and your career is over! He is really worried that he can not
play the same character over and over again as he will become too predictable. On the other hand, he also fears falling
into the other extreme, i.e. playing several types of role without forging a clear identity. What should he do? Well,
let's help him with some data analysis!

**The spectrum of ratings**

Bob really wants to maximise the income from the films he plays in. Unfortunately, only a handful of films are able to
make it to the box office. Indeed, in the movie dataset almost 90% of movies do not have a box-office revenue!
Bob is still a newcomer to this industry and can not play in those big blockbusters yet. Nonetheless, he remembers why
he wanted to become an actor in the first place. Even though money is important, Bob's priority was to move people's hearts! 

Therefore, let's have a look at the movies' ratings. In our analysis, we choose the IMDb database. As we'll see, it's less
about the extremes and more like a cozy middle part of the road party. 

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/ratings_histogram.html"></iframe>
</div>

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/movie_votes.html"></iframe>
</div>

We can notice from the distribution of movie ratings that fewer movies receiving very low or very high ratings, with a
slight tendency of voters to rate movies positively. The "number of movies over number of votes" plot tells us that only
a small number of movies receive a large number of votes.

What has influence over this popularity? Is it memorable characters, or the star power of actors? Should Bob play the same
type of character over and over again to create a sense of comfort in the public, or does he need to keep reinventing himself
to surprise the audience? To uncover the best strategy for Bob, he needs to know what sort of roles he needs to play.
Can he stick to play those menacing villains like Darth Vader during his whole career?

Let's see how many characters actors usually play.

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/actor_roles.html"></iframe>
</div>

Only a few famous actors have plethora of multiple roles. Only 16% of actors have more than 5 roles. It turns out
the movie industry's got a "type," and not many actors fit into it. The big names might be playing it safe in their
cinematic comfort zone.

### Character tropes: success or visibility ?

This bifurcation raises intriguing questions: Do more tropes equate to greater success, or simply greater visibility?
Is the industry inclined to favor a selected group and to typecast actors, or do these actors possess an adaptive
chameleon-like quality that lands them role after role, or simply actors tend to have a preference to play some roles
more than others ? We defined metrics that help us understand to what extent actors prefer certain types of characters,
or personas, in their careers.

Conceptually, let's imagine that Alice takes a random role in our dataset and among the different personas that make up
this role, she chooses one persona randomly with probabilities proportional to the proportion of the persona for this
role (i.e if a role is 50% "bad guy" and 50% "big muscled guy", then Alice has 50% of chance to choose the "bad guy"
persona and likewise for the "big muscled guy"). Our best shot to guess which persona she took would be to take the most
represented persona:

<div class="row">
  <div class="small-column">
    <span class="helper"></span> <img src="assets/img/alice_portrait.jpg" class="portrait-img" alt="DefaultPortrait" style="width:100% ">
  </div>
  <div class="big-column">
    <iframe class="fixed-iframe" src="assets/plot/persona_global.html" ></iframe>  
  </div>
</div>

In our case, this would be the persona 50. The 5 most important verbs for this persona are: "put", "read", "drive", "stay" and "feel".
We get the impression that we're dealing with a character with no personality, a generic character who is only there to
fill the void on the screen. But now, let's suppose that I tell you that Christopher Lee (the one who played Count Dooku,
one of Bob's favourite characters) is the one who played this role!

<div class="row">
  <div class="small-column">
    <span class="helper"></span> <img src="assets/img/christopher_lee.png" class="portrait-img" alt="ChristopherLee" style="width:100% ">
  </div>
  <div class="big-column">
    <iframe class="fixed-iframe" src="assets/plot/christopher_lee_persona.html" ></iframe>  
  </div>
</div>


Now our answer would be different because **we gained information about the mystery persona**. Indeed, Christopher Lee
tends to always play the same persona: the bad guy! He is Count Dooku, Saruman, Dracula, ... If we look at the most
represented personas for Christopher Lee, we see that Persona 36 and 34 are much more represented than the other ones.
Here are the top verbs for both personas:
- Persona 36: "go", "turn", "put", "throw", "reveal", "keep"
- Persona 34: "recognize", "arrange", "place", "set", "invite", "threaten"

Persona 36 seems to be a generic persona without too much obvious structure, though "turn" and "reveal" can indicate a key
role. Persona 34 is much more interesting. Words like "threaten", "arrange", "place", "set" and "invite" suggest that
this persona captures some sort of manipulative villain which is very fitting for an actor like Christopher Lee!

In this case, we gained a lot of information about the "mystery persona" **because Christopher Lee's roles revolve around
a couple of tropes**. In the other extreme, if an actor tends to play personas that are very uniform,
then we would actually lose information about this "mystery persona".

#### Mutual Information Preference score of personas: 

With this key idea of information gain we design our first key metric: the **mutual information preference metric, MIP**. 
The MIP score for each trope distribution reveals how closely an actor's choices align with, or diverge from, the
collective narrative palette. An actor whose range of personas closely matches the global distribution would have an MIP
score approaching zero, suggesting a versatile adaptability to the myriad roles the industry offers. In contrast, actors
with higher MIP scores tend to have a more specialized or distinctive selection of character tropes, indicating a niche
or a strong association with particular kinds of roles.
In other words, MIP can tell us whether an actor's repertoire is not particularly special or stands out from the crowd.

1. A MIP score of 1 signifies an actor with a singular focus
2. An MIP score of 0 indicates an actor whose choices mirror the global distribution of roles or genres.
3. Any value in-between reflects a polarization of a certain degree

For each actor we have computed an "average persona", which is taken over all characters they played. We compute the MIP
of this average persona and report the density of actors over MIP scores below.

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/mip_personas.html"></iframe>
</div>

As we can observe, the average persona's MIP score of actors tends to be around 0.4, meaning a relatively average polarisation of roles.
The histogram is bell-shaped with a substantial spread. This distribution indicates that while there's a strong central
tendency — most actors have an average degree of persona specialization. The very high spike in density at 1 is due to
actors for which the average persona was fully polarized, that is they only played a single persona accross their movies.
These are likely actors who have only played relatively few movies, or found a niche for which they are frequently typecast.
The thinner left side, shows fewer actors who are characterized by a wide variety of roles, the industry's versatile figures 
and chameleons, leaping from role to role.

The plot highlights the extremes: We have a lot more actors with high MIP scores, often stepping into an electic array
or roles and tend to be more predictable in their role choices. The right spike presents us the specialists that have found 
their niche. We naturally ask: Do these specialization trends observed in persona choices also mirror the genres that actors are drawn to?

#### Mutual Information Preference score of genres
**TODO : move cette partie après "Character tropes: success or visibility ?" ?**

We apply roughly the same process on movie genres. For each actor, we recover all the movies they played in and the
genre distribution of those movies. Using this information and the global genre distribution we compute an second MIP
score for each actor. Note that we don't need to use averages here, because this genre distribution is not affected by
a particular movie, in contrast to personas which differ for each character within a given movie.

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/mip_genre.html"></iframe>
</div>

The MIP metric, when applied to genres, tells a story about an actor's alignment with the industry's genre landscape.
The distribution is much more concentrated around 0.25 and has minimal spread. This distribution of actors across genres
raises questions about the forces that shape an actor's career trajectory. Is it personal inclination, the allure of
certain types of stories that resonates with their own artistic voice? Or does it reflect the typecasting tendencies of
an industry that finds a formula and sticks to it, sometimes to the detriment of creative diversity?

#### The love calculator between an actor and a role

Although Bob really likes to play the villain (like his idol Christopher Lee), he knows that he can not play this persona for his entire carreer. Even Christopher Lee, the embodiment of villainess, played a good guy like Sherlock Holmes! In general, even if they have a preference towards some personas, actors sometimes need to act out of their comfort zone. Are they more successful when they play out of their comfort zone? To determine if an actor is out of his comfort zone **for a given role**, the MIP metric is not enough.

Let's use Christopher Lee as our example once again but this time we will look at the genres that he plays. 

<div class="row">
  <div class="small-column">
    <span class="helper"></span> <img src="assets/img/christopher_lee.png" class="portrait-img" alt="DefaultPortrait" style="width:100% ">
  </div>
  <div class="big-column">
    <iframe class="fixed-iframe" src="assets/plot/christopher_lee_genres.html" ></iframe>  
  </div>
</div>

Here we only plot the genres with more than 1% frequency in his filmography. He seems to have a clear tendency to play in Horror and Thriller like movies such as _Dracula_ (labeled as **Horror** and **Thriller** movies in our dataset). Since both of the most represented genres are included in _Dracula_, we can assume that Christopher Lee has some degree of comfort in playing in this movie.

On the other hand, one of his other movies _the Mummy_ has genres **Horror**, **Archeology** and **Monster movie**. **Archeology** and **Monster movie** don't even represent 1% of Christopher Lee's played genres. He clearly stepped out of his comfort zone for this role! The reasoning is that the distribution of genres for this movie is very "far" from the global distribution of Lee's genres. To quantify this notion of "distance", we use the relative entropy (also known as Kullback–Leibler divergence).

<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/genres_kld_histogram.html"></iframe>
</div>
<div class="container">
  <iframe class="responsive-iframe" src="assets/plot/personas_kld_histogram.html"></iframe>
</div>

We use the same idea to compute the Kullback-Leibler divergence for the personas. The plot for personas shows a very noisy Gaussian with a spike at 0. This may be explained by the fact that a lot of actors tend to play the same type of persona over and over again.

#### So? What should Bob do?

After those very long explanations, we are finally ready and set to answer our question!

### OLS Guillaume

To investigate whether there is a notable difference in the performance of movies when a certain actor steps out of his usual roles, we embark on a statistical journey, exploring how the specialization of actors in their roles (**`mip_trope`**) and their propensity to engage in familiar roles (**`trope_likelihood`**) impact a movie's reception, as measured by its average rating.  These are the two independent variables in Ordinary Least Square regression. that reflect the tendency of actor sticking to their comfort zones. 



 **Plot twist:** Intuitively, we sensed that actors excelling in familiar roles potentially enhances a movie's performance. But, as any good story, there is a twist. The OLS revealed a negative correlation where comfort and specialization dragged down movie ratings with confidence intervals at  [-1.070, -0.885] and [-0.273, -0.230] respectively. Wait, there is more to find out here. The low R-squared value of 0.001 subtly suggests that there is more to the story.

While **`mip_trope`** and **`trope_likelihood`** play a role on the movie ratings, they are not the main influencers. There's likely another key factor that might be an unseen confounder variable. This search of understanding never truly ends.


### Fares plots and analysis

