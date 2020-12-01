# Effect Strategies

*Effect Strategies are being used to compute effect sizes of every outcome variables in an Experiment.* Like most methods, we configure an Effect Strategy by specifying the method name, and its appropriate parameters, if any.

!!! experiment "Configuration: Effect Strategy"
	```json hl_lines="6 7 8"
	{
		"experiment_parameters": {
			...,
			"data_strategy": {...},
			"test_strategy": {...},
			"effect_strategy": {
			    "name": "MethodName"
			}
		}
	}
	```

## Mean Differences

- [ ] TODO: Add descsription and reference

$$d = \mu_1 - \mu_2$$

```json
"effect_strategy": {
    "name": "MeanDifference"
}
```

## Standardized Mean Differences

- [ ] TODO: Add descsription and reference

$$d = \frac{\bar{x}_1 - \bar{x}_2}{s} = \frac{\mu_1 - \mu_2}{s}$$

where $s$ is an average standard deviation of both groups, $\sqrt{\frac{s_{1}^2 + s_{2}^2}{2}}$, where the variance for one of the groups is defined as

$$s_i^2 = \frac 1 {n_1-1} \sum_{i=1}^{n_1} (x_{1,i} - \bar{x}_1)^2$$

```json
"effect_strategy": {
    "name": "StandardizedMeanDifference"
}
```

## Cohen's D

- [ ] TODO: Add descsription and reference

$$d = \frac{\bar{x}_1 - \bar{x}_2}{s} = \frac{\mu_1 - \mu_2}{s}$$

where $s$, the _pooled standard deviation_ is defined as:

$$s = \sqrt{\frac{(n_1-1)s^2_1 + (n_2-1)s^2_2}{n_1+n_2 - 2}}$$

where the variance for one of the groups is defined as

$$s_i^2 = \frac 1 {n_1-1} \sum_{i=1}^{n_1} (x_{1,i} - \bar{x}_1)^2$$

```json
"effect_strategy": {
    "name": "CohensD"
}
```


## Hedge's G

- [ ] TODO: Add descsription and reference


```json
"effect_strategy": {
    "name": "HedgesG"
}
```