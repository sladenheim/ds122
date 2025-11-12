# My notes

## Timeline

Lisa ends lecturing with L27 on 11/10, and I start on 11/12

That means I have 10 lectures to work with, L28 through L37.


**L28 - Poisson Processes** 
- Mixture distributions (adding, subtracting, mixing)
- Poisson processes & World Cup problem
- Probability of superiority

**L29 - Bayesian Testing & Decision Making** 
- Euro problem revisited with Bayes factors
- Bayesian hypothesis testing
- Bayesian bandits (Thompson sampling)

**L30 - Comparison**
- Comparing two distributions (height example or better sports example)
- Posterior predictive distributions
- Applications to A/B testing

**L31 - Classification (Naive Bayes)**
- Naive Bayes classifier
- Penguin example with visualizations
- Multinomial vs multivariate normal

**L32 - Conjugate Priors Part 1**
- Motivation: grid method vs analytical
- Beta-Binomial (Euro problem)
- Return to exponentials, intuition about "pseudo-data"

**L33 - Conjugate Priors Part 2** 
- Gamma-Poisson (World Cup revisited)
- Dirichlet-Multinomial (Lions/Tigers/Bears)
- Table of conjugate pairs

**L34 - Monte Carlo Methods** 
- Monte Carlo integration (better motivating example)
- Pseudo-random generation
- Accept-reject sampling
- Bridge to MCMC

**L35 - MCMC Part 1** 
- Motivation: high-dimensional posteriors
- Markov chain steady states revisited
- Metropolis-Hastings algorithm (theory)
- Simple example (Good King Markov or similar)

**L36 - MCMC Part 2** 
- Detailed balance and why MH works
- Proposal distributions
- Burn-in and convergence diagnostics
- Euro problem with MCMC implementation

**L37 - MCMC in Practice** 
- PyMC introduction
- Bayesian regression example
- Comparing to frequentist regression
- Best practices and diagnostics

### Old lecture names:
- poisson processes
- bayesian testing
- comparison and classification
- bayesian inference
- conjugate priors
- monte carlo
- MCMC
- MCMC in practice

### new syllabus week names:
- probability of superiority and bayesian bandits
- naive bayes
- conjugate priors
- markov chain monte carlo

## Lecture notes from my sections

#### Poisson processes
- D&D example is a bit off (so is the photo) - one weapon strictly dominates the other
- Motivate world cup problem earlier - the mixture modeling stuff feels unmotivated
- Define gamma distribution when I name  (The exponential distribution, Erlang distribution, and chi-squared distribution are special cases of the gamma distribution)
- Before using scipy gamma look up parameters and show defaults / motivate using parameters set

#### Bayesian testing - excited about this one! Theme is gambling?
- Euros - Add multiple distribution of what a biased coin looks like - fair coins have between 49 and 51 (look up factual data on this?), unfair coins unlikely to be like 51.5 (pointless) or 99.9 (would give it away).  And prior belief dependent on the situation - are you at a casino, friends house, street hustler? - give sliders / options here and play with results
- Bandits (hard to grasp) - simulate strategies, they watch the posteriors, vote on what they think will work well, make it interactive so they call out what to click next and explain why - then give the optimal alg / thompson sampling at the end.

#### Comparison and classification (naive bayes)
- **Comparison**: The height problem isn't super motivating? Nice simple math though.  What's better than height.... stay in sports and do the height of basket ball players? (Or do that as a variation?) Show a slider of posteriors of A and B and the slider is the perceived difference?  Show how that's different if the curve isn't normal (eg heights of actors, bb players, etc)
- Classification
	- Penguins - actually show pictures of each type of penguin
	- Describe difference with multivariate normal - show the different shape of the multinomial
	- Show complete accuracy results for both
- Inference
	- Can be hard b/c tensors are confusing, need a lot of visuals - ??? - where are there tensors? Maybe in the slides?
	- Wow DALLE pictures are baaad 

#### ‼️ Conjugate priors
- Return to the sports problem / poisson process
- Remember grid process - is there a better way?  What if we could express our prior as a distribution, and somehow also get our posterior as a distribution, rather than a table of values?
- Add a slide on exponentials (`e^x e^y = e^(x+y)`) 
- Back to Euro coins - beta-binomial, alpha is "prior heads", beta is "prior tails" - nice relationship where belief distributions stays the same, easy to compute

- Let's derive this for poisson processes
- Then multinomial / dirichlet

- Show equivalence - you CAN still do a grid for these, and when you sum it up you get the equations again
- Table in the end is important / they need for exam

- "In some sense a conjugate prior acts similarly to adding "pseudo data" to the data observed, and then estimating the parameters." [Link](https://stats.stackexchange.com/questions/176668/can-anyone-explain-conjugate-priors-in-simplest-possible-terms) <- **maybe a good way to position** the whole thing? Especially as a data-focus
- [Another reference](https://www.statlect.com/fundamentals-of-statistics/conjugate-prior)

#### Monte Carlo
- Arbitrary integral example feels silly, also you could integrate it.  But what if you had a wild curve (draw something crazy / sinusoidal) - in calculus you made little rectangles (show) and the limit approached the area, but another idea is throwing darts at it and that approaches the area too... (prove it's the same with a toy problem / show animation)
- I like the pseudo-random generation thing
- Can I find a good motivating example here? (Ask Claude?) lecture's not too bad though, just a bit boring
- Eg. Random draws of a poker hand? Reject invalid /repeating ones?  That lets us compute probabilities of different hands without worrying about joint distributions?

#### ‼️ MCMC - 2 or 3 
- Idea: MCMC lecture, calculate Pi to accept/reject thinking about generating random numbers, interlude for even generating uniform values
> They understand accept/reject but struggle connecting it to markov chains
- The average test scores example is boring and contrived (how could the instructor know the std is 15?) - also starting with a guess like 110 for a mean makes noooo sense?
- It introduces the algorithm out of thin air with a crazy situation...
- Then it goes to a VERY abstract "5 state" markov chain with random values?
> The key idea is to set the transition probabilities of the Markov chain so as to ensure that the steady-state of the chain will be the distribution we want to sample
- Focus on that.  Two ideas - using MCMC to measure steady state distributions of a markov chain, and making a markov chain that represents a distribution we want to understand.
- Want to include a proof here actually that Metropolis-Hastings gives the right thing.

- MCMC example - going door to door to find distribution of a teams fans Or random sampling to determine population for census, representatives 
- Then PyMC / MCMC for bayesian regression as another lecture - want to better motivate that with a better problem / compare to frequentist regression

Good example from Michael:
- Good king markov and his islands example for MCMC
- https://rpruim.github.io/Kruschke-Notes/markov-chain-monte-carlo-mcmc.html
- https://bookdown.org/content/4857/markov-chain-monte-carlo.html



