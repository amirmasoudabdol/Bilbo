# Meta Analysis

[Meta analysis](https://en.wikipedia.org/wiki/Meta-analysis) methods are being used by Journal for two main purposes:

1. **Meta-Analytic Outputs**. Journal may use the specified meta-analysis methods to combine  result of multiple studies, ie., [**publications list**](/journal-configuration.md), at the end of each  simulation cycle, ie., when it has collected `max_pubs` publications. 
2. **Adaptive Selection Strategies**. Journal may use the meta-analytic outcomes to adjust its [Selection Strategy](/selection-strategies.md) and its acceptance rate. [under development]


## Meta-Analytic Outputs

Collecting meta-analytic outputs is the main use-case of adding meta-analysis methods to Jouranl's configuration.
This is done by adding each method to a list of `meta_analysis_metrics` under `journal_parameters` section. Like before, we can add any method-specific parameters to the list. In the case where we prefer using one method with two sets of different parameters, we can simply add a new method with the modified parameters.

After each simulation cycle, when the list of [accepted publications](/journal-configurations.md) is ready, Journal traveses through the list of methods, and computes their outcomes. Before restarting the simulation — and getting ready for a new set of submissions to arrive — Journal saves all its publications, and their corresponding meta-analyses to different CSV files for further analysis by the user. [Simulation configurations](/simulation-configurations.md) section lists all the different available output parameters.

```json hl_lines="4 5 6 7 8 9 10 11 12 13 14"
"journal_parameters": {
	"max_pubs": 24,
    "selection_strategy": {...},
    "meta_analysis_metrics": [
        {
            "name": "MethodName",
            "param": ...
        },
        {
            "name": "MethodName",
            "param": ...
        },
        ...
    ]
}
```

SAM offers a short list of meta-analysis methods and publication bias metrics, as presented in the rest of this section.

### [Fixed Effect](https://en.wikipedia.org/wiki/Fixed_effects_model) Estimator

!!! journal "Fixed Effect Estimator Configurations"
	```json
	{
	    "name": "FixedEffectEstimator"
	}
	```


### [Random Effect](https://en.wikipedia.org/wiki/Random_effects_model) Estimator

!!! journal "Random Effect Estimator Configurations"
	```json
	{
	    "name": "RandomEffectEstimator",
	    "estimator": "DL"
	}
	```
List of available estimators are:

- DerSimonian-Laird Estimator[@DerSimonian_1986]

### Egger's Test Estimator[@Egger_1997]

!!! journal "Egger's Test Estimator Configurations"
	```json
	{
	    "name": "EggersTestEstimator",
	    "alpha": 0.1
	}
	```


### Trim and Fill Method[@Duval_2000]

!!! journal "Trim and Fill Method Configurations"
	```json
	{
	    "name": "TrimAndFill",
	    "alpha": 0.1,
	    "estimator": "R0",
	    "side": "auto"
	}
	```


### Begg's Rank Correlation[@Begg_1994]

!!! journal "Rank Correlation Configurations"
	```json
	{
	    "name": "RankCorrelation",
	    "alpha": 0.1,
	    "alternative": "TwoSided"
	}
	```


### Test of Excess of Significant Findings[@Ioannidis_2007]

!!! journal "Test of Excess of Significant Findings Configurations"
	```json
	{
	    "name": "TestOfObsOverExptSig",
		"alpha": 0.1
	}
	```

---

## Adaptive Selection Strategies



\bibliography