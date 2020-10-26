# Effect Strategies

Effect Strategies are being used to compute effect sizes of every outcome variables in an Experiment. 
Like most method, we configure an Effect Strategy by specifying the method name, and its appropriate parameters, if any.

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

```json
"effect_strategy": {
    "name": "MeanDifference"
},
```

## Cohen's D

```json
"effect_strategy": {
    "name": "CohensD"
},
```


## Hedge's G


```json
"effect_strategy": {
    "name": "HedgesG"
},
```