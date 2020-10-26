# Selection Strategies

Two primary built-in selection strategies are Random Selection and Significant Selection. While the former algorithm flips a coin for accepting each submission, the latter simulates the publication bias phenomena.

## Random Selection

Random selection method is the simplest form of selection where Journal flips a coin to decide whether a submission is going to be accepted or not. Using **p = 0** will lead to a Journal that does not accept anything, and **p = 1** defines a Journal that accepts everything.

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

As the name suggest, significant selection strategy incorporates the concept of publication bias [cite] into his decision. Therefore, a submission will be accepted if it is significant, if not, it will have a (1 - Pʙ) chance of being accepted.


!!! journal "Sifnigicant Selection"
	```json
	"journal_parameters": {
		"selection_strategy": {
			"name": "SignificantSelection",
			"alpha": ɑ,
			"journal_pub_bias": Pʙ,
			"side": 0
		}
	}
	```


## Policy Based Selection

As the name suggest, policy based selection strategies are using [policy chains](/decision-strategies.md#policy-chain) to evalute the "quality" of a submission, and therefore come to their verdict.


!!! journal "Policy Based Selection"
	```json
	"journal_parameters": {
		"selection_strategy": {
			"name": "SignificantSelection",
			"journal_pub_bias": Pʙ,
			"acceptance_policy": ["effect > 0", "sig"]
		}
	}
	```


!!! journal "Policy Based Selection"