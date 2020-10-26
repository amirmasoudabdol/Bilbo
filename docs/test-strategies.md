# Test Strategies

*Test strategy defined the method of hypothesis testing.* After collecting data, 
Researcher runs the test on Experiment, and calculates appropriate statistics, 
and *p*-values for each outcome variables. Thereafter, based on the calculated *p*-value, and given ɑ,
Test Strategy decides whether the test result is significant or not.

Similar to Data Strategy, we configure a Test Strategy by specifying the method name, and then setting
their specific parameters as follow:

```json hl_lines="5 6 7 8"
{
	"experiment_parameters": {
		...,
		"data_strategy": {...},
		"test_strategy": {
	    	"name": "MethodName",
	    	"alpha": 0.5
		}
	}
}
```

Most tests should be accompanied by an ɑ level. This ɑ is going to be used throughout the rest of SAM to evaluate the 
significance level of an outcome. For instance, when a [policy](/decision-strategies.md#policy) queies significance, SAM asks Test Strategy to see whether for a given outcome, the test is significant or not.


## T-Test

In order to configure a [t-test](https://en.wikipedia.org/wiki/Student%27s_t-test), we need to set some general parameters, as follow:

!!! teststrategy "T-Test Configurations"
	```json
	"test_strategy": {
	    "name": "TTest",
	    "alpha": 0.05,
	    "alternative": "TwoSided",
	    "var_equal": true
	}
	```

## F-Test

!!! teststrategy "F-Test Configurations"
	```json
	"test_strategy": {
	    "name": "TTest",
	    "alpha": 0.05
	}
	```

## Yuen T-Test[@Yuen_1974]

!!! teststrategy "Yuen Test Configurations"
	```json
	"test_strategy": {
	    "name": "YuenTest",
	    "alpha": 0.05,
	    "alternative": "TwoSided",
	    "trim": 0.2,
	    "paired": true
	}
	```

## Wilcoxon Test[@Wilcoxon_1992]

!!! teststrategy "Wilcoxon Test Configurations"
	```json
	"test_strategy": {
	    "name": "WilcoxonTest",
	    "alpha": 0.05,
	    "use_continuity": true
	}
	```

\bibliography