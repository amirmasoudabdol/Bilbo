# Selection Strategies

Two primary built-in selection strategies are Random Selection and Significant Selection. While the former algorithm flips a coin for accepting each submission, the latter mimics the publication bias phenomena. Besides these two strategies, more elaborate selection strategies can be deployed at Journal. In this section we list a few of the available strategies.

## Free Selection

With free selection method, Journal does not impose any restriction during the reviewing process and every submission applied for the review is going to be accepted. This strategy is suitable for cases where we are interested in the intact population of the publications rather.

!!! journal "Free Selection"
	```json
	"journal_parameters": {
		"selection_strategy": {
			"name": "FreeSelection"
		}
	}
	```

## Random Selection

Random selection method is the simplest form of selection where Journal flips a coin to decide whether a submission is going to be accepted. Using **p = 0** will lead to a Journal that does not accept anything, and **p = 1** defines a Journal that accepts everything.

!!! journal "Random Selection"
	```json
	"journal_parameters": {
		"selection_strategy": {
			"name": "RandomSelection",
			"probability": p
		}
	}
	```


## Significant Selection (Biased Selection)

As the name suggests, the *significant selection strategy* incorporates the concept of publication bias [cite] into Journal's review process. Therefore, a submission will be accepted if it is significant, if not, it has a (1 - Pʙ) chance of being accepted.

!!! journal "Sifnigicant Selection"
	```json
	"journal_parameters": {
		"selection_strategy": {
			"name": "SignificantSelection",
			"alpha": ɑ,
			"pub_bias": Pb,
			"side": 0
		}
	}
	```


## Policy Based Selection

Policy based selection strategy are using [policy chains](/decision-strategies.md#policy-chain) to evalute the "quality" of a submission, and therefore come to their verdict. In addition to the given criteria, we can adjust the *acceptance rate*, `pub_chance`, and the *publication bias rate*, `pub_bias`. Journal first evaluates whether the `selection_policy` can be satisfied; then, a random draw decides whether the publication is lucky enough to be accepted, and finally, odds of being actually published will be evaluted against the publication bias rate.

Notice that the flexibilty of the selection policy and availability of publication bias rate will allow for construction of Journals with specific biases, e.g., positive effects, large study sizes, etc.


!!! journal "Policy Based Selection"
	```json
	"journal_parameters": {
		"selection_strategy": {
			"name": "PolicyBasedSelection",
			"selection_policy_defs": ["effect > 0", "sig"],
			"pub_chance": Pc,
			"pub_bias": Pb
		}
	}
	```
