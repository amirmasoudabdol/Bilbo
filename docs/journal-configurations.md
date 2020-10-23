---
title: Introduction
---

# Journal Configuration



At the end of the [research workflow](research-workflow.md), Researcher has either decided to discard his research, or, is preparing to submit his final submission to the Journal. At this point, he passes his manuscript to Journal, and therefore will have no control over its destiny anymore. 

Journal module is designed to simulate the reviewing process. After receiving the submission (ie. Manuscript) from Researcher, Journal asses whether to accept or reject the submission. Journal’s assessment is being conducted using groups of pre-defined algorithm, or criteria. We are referring to as *Selection Strategies*. 

![<b>Figure 1.</b> Journal’s Reviewing Workflow](journal-review-workflow.md)

Figure 1 shows the steps taken by Journal during the review process. Journal starts by querying the selection strategy for its verdict on whether the given submission is suitable for publication or not. For example, a selection strategy that’s designed to simulate *publication bias* might base its decision on availability of positive significant effect, and therefore reject 95% of non-significant results. 

If selection strategy approves the “quality” of the submission, submission will be accepted and stored in a database of accepted outcomes, a.k.a, **publications list**. In contrast, rejected outcomes will not be published and stored in **rejected submissions**. At the end of the simulation, journal may export any or all of these lists as CSV files for further analysis.

	Journal parameters are less elaborate than other modules and are divivded into three main parts, [Selection Strategy](selection-strategies.md) and [Meta Analysis](meta_analyses.md).


	- **`max_pubs`**, *`double`*, Maximum number of publications that will be cepted by the `Journal`.
	- **`selection_strategy`**, *`string`*, The `SelectionStrategy` of the journal. 
	- **`meta_analysis_metrics`**, *`list`*, List of meta anlysis methods with their parameters, see [Meta Analysis](meta-analyses.md)


## Selection Strategies

Two primary built-in selection strategies are Random Selection and Significant Selection. While the former algorithm flips a coin for accepting each submission, the latter simulates the publication bias phenomena.

### Random Selection

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


### Significant Selection (Biased Selection)

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


### Policy Based Selection

As the name suggest, policy based selection strategies are using [policy chains](decision-strategies.md#policy-chain) to evalute the "quality" of a submission, and therefore come to their verdict.


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