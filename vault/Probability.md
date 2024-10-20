
Bayesian vs frequentist
Updating belief of the world
Apriori
[[Markov process]]
[[Martingale]]

Probability primer
Recurring definitions
State estimation - where am I, what does the world look like
Localization
Mapping
SLAM
Navigation
Motion planning
Probabilistic approaches
Uncertainty in motion and sensors
Theory allows to explicitly model uncertainties, roughly 90% of techniques rely on it
Axioms of probability theory - 0 to 1, probability of a or b is pr(a) + pr(b) - pr(a and b)
Discrete random variables - random variable can only take specific values, probability mass function
Continuous random
Joint and conditional probability
If independent, px*py
If x given y, pxandy/py
Law of total probability - get x by summing of all outcomes of y
Px is sum of all pxgiveny*py
Marginalization - get x by summing all joint probability with y
Working through examples with actual numbers
Bayes Rule - switching xgivy and ygivx, likelihood * prior / evidence
With background knowledge z
Conditional independence - 2 variables xy are independent given z
Does not imply marginal independence
Normal distribution
Gaussian Mixture - multi-modal, combination of multiple normal distributions
Summary - probability theory is essential tool to solve state estimation, used for recursive bayes filter

References
Probability statistics 110 by harvard
http://youtube.com/playlist?list=PL2SOU6wwxB0uwwH80KTQ6ht66KWxbzTIo