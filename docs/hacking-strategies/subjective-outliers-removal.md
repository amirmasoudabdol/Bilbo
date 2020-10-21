# Subjective Outliers Removal

Subjective outliers removal is defined by Bakker et al., 2014[@Bakker_2014] as a special and even more questionable case of outliers removal where the researcher lowers *k* (the threshold of considering an item to be an outlier) dynamically during the data analysis.

While we are able to mimic this behavior by tweaking the parameters of [outliers removal](/hacking-strategies/outliers-removal.md), SAM has a built-in hacking strategy for this specific method. 


!!! hackingstrategy “Subjective Outliers Removal”
		```json
		{
			"name": "SubjectiveOutlierRemoval",
			"min_observations": 5,
			"range": [
				2,
				3
			],
			"step_size": 0.5,
			"stopping_condition": [
				"sig"
			]
		}
		```
	
The main difference between this algorithm, and general outliers removal is that fact that SAM generates an array of equally distant *k*’s between the given `range` using the given `step_size`. For instance, in the above example, a range of *k*’s will be {3, 2.5, 2}. Notice that the algorithm starts from highest to the lowest *k*.


\bibliography

