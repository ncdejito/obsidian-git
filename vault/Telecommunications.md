
[[Graph Theory]]

TM Forum newsletter

Title: Patterns, Entropy, and Predictability of Human Mobility and Life

Key takeaways:

Input: 500 users Finland, 3 years data, pruned to 66users, location bts, hour aggregate activity

Output: typical places, measure of predictability of locations that a person will visit, predict next location of a person few hours ahead

Method:

Cluster cells using offline clustering(?) and fingerprint based method
Find top location for each time slot using majority rule(?)
Pad missing timeslots as extension of stay at location (user X  closes phone at home from 1pm-5pm)
Exclude days with more than 30% missing data
Find similar, “typical” days by clustering days using kmeans and community detection

Title: Limits of Predictability in Human Mobility

Key takeaways: Hourly regularity method

Input: 50K users, 3months, location tower cdr

Output: measure of predictability in human mobility (93%)

Method:

Filter only users that visit more than two locations and call frequency >0.5/h, get 50Kusers
For each user, create network of towers visited (nodes) with links representing movement between towers
Calculate random entropy log2N number of distinct locations visited, degree of predictability if user visited each location equally
Calculate temporal-uncorrelated entropy -pi(j)log2pi(j) where pi(j) is historical probability that user i visited location j, characterizing how distributed a person’s visitation pattern is
Calculate actual entropy -P(T’)log2P(T’) where P(T’) is probability of observing trajectory T’ in T where T is time ordered sequence of towers visited, characterizing frequently occurring paths in a person’s mobility footprint
Measure how representative a user’s data is by checking how many hour intervals actually have location, q which represents hour intervals no location over total hour intervals, users have unknown location >70% of the time
<revisit logic> Real uncertainty about user’s whereabouts is fewer than 2 locations
<revisit logic> significant share of predictability is encoded in temporal order of visitation
For each user for each hour in 24x7 hourly intervals, calculate top location
<revisit logic> around 70% of the time, top location coincided with actual location


Title: Understanding individual human mobility patterns

Key takeaways:

Input: 100K users, 6months, CDR

Output: humans follow simple reproducible patterns

Method:





