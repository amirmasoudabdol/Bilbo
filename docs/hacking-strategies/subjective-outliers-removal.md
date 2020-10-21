# Subjective Outliers Removal

Subjective outliers removal is defined by Bakker et al. 2014 as a special and even more questionable case of outlier removal where the researcher lowers `k` (the threshold of considering an item to be an outlier) dynamically during the data analysis.

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

\bibliography

