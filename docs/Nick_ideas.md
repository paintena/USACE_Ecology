# Ideas for how to model:

## Data driven model
	1. Derive suitability function/distribution.  That is, for a given depth and height, compute the suitability.  Attempt to fit this to the data as "best" as possible. (Bayesian Model Selection?)
	2. Given the suitability function, derive the domain suitability.
		* Given the size of the data, we may want to perform some aggregation here to ensure that the computation is doable in a reasonable time.
		* Look for correlated areas, these may represent a reasonable community?
	3. Using the above suitability distribution, attempt to establish "livable communities".  Do some sort of cluster analysis or other algorithm to group together regions.
		* Attempt to define locations that are locally similar.  (HARD!!!)
	4. Establish a network between the suitable regions where the edges of the network are determined, in some way, from the gradient of the suitability function.  
		* Locations that are far away from the current location would be "Very hard" to travel to, so the weights on these edges should be very small.
		* If a region is close and more suitable, we can assume that the species may try and migrate to that new region
		* Look at the famous path feeding model for ideas?  Look at citations of that paper.
	5. Attempt to find the stationary distribution of the derived network (assuming that we have formulated it in the sense of a Markov Process).

Pros (+) and Cons (-)
+ Natural work flow to follow	
+ Attempts to use as much of the data as possible
+ Works more naturally and unbiasedly from the data	
- Can't be easily modified for more complexity
- May be computationally hard

	
## Direct modelling
	1. Develop evolution equations that explain how the salmon move within the domain, given local depth and velocity.
	2. Use a metered model for the salmon and assume that, rather than diffusion, they move in accordance to environmental factors (and some small amount of diffusion).

Pros (+) and Cons (-)
+ More easily generalizes to more complicated ecosystem	
+ Easily modifiable
- May not rely directly upon data
- Relies on "guessing" functional forms
- Computationally much harder
