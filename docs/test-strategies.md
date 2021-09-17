# Test Strategies

*Test strategy defines the method of hypothesis testing.* After collecting data, the Researcher runs a statistical test on the Experiment, and calculates appropriate statistics, and *p*-values for each outcome variables. Thereafter, based on the calculated *p*-value, and given ɑ, *Test Strategy decides whether the test result is significant.*

Similar to Data Strategy, we configure the Test Strategy by specifying the method name, follwing with its setting their specific parameters. Most tests should be accompanied by an ɑ level. This ɑ is going to be used throughout the rest of SAM to evaluate the significance level of an outcome. For instance, when a [policy](decision-strategies.md#policy) queies for significance of an outcome, SAM asks Test Strategy to see whether for a given outcome, the test is significant.

!!! teststrategy "Configuration: Test Strategy"
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

While SAM offers a few test strategies out of the box, it is possible to extend this list by implementing your own methods using the provided API.

## T-Test

- [ ] TODO: Add descsription and reference

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

- [ ] TODO: Add descsription and reference

!!! teststrategy "F-Test Configurations"
	```json
	"test_strategy": {
	    "name": "TTest",
	    "alpha": 0.05
	}
	```

## Yuen T-Test[@Yuen_1974]

- [ ] TODO: Add descsription and reference

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

- [ ] TODO: Add descsription and reference

!!! teststrategy "Wilcoxon Test Configurations"
	```json
	"test_strategy": {
	    "name": "WilcoxonTest",
	    "alpha": 0.05,
	    "use_continuity": true
	}
	```

\bibliography