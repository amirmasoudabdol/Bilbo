---
title: Introduction
---

# Journal Configurations

At the end of the [research workflow](research-workflow.md), Researcher has either decided to discard his research, or, is preparing to submit his final submission to the Journal. At this point, he passes his manuscript to Journal, and therefore will have no control over its destiny anymore. 

Journal module is designed to simulate the reviewing process. After receiving the submission (ie. Manuscript) from Researcher, Journal asses whether to accept or reject the submission. Journal’s assessment is being conducted using groups of pre-defined algorithm, or criteria. We are referring to as *Selection Strategies*. 

![<b>Figure 1.</b> Journal’s Reviewing Workflow](journal-review-workflow.md)

Figure 1 shows the steps taken by Journal during the review process. Journal starts by querying the selection strategy for its verdict on whether the given submission is suitable for publication or not. For example, a selection strategy that’s designed to simulate *publication bias* might base its decision on availability of positive significant effect, and therefore reject 95% of non-significant results. 

If selection strategy approves the “quality” of the submission, submission will be accepted and stored in a database of accepted outcomes, a.k.a, **publications list**. In contrast, rejected outcomes will not be published and stored in **rejected submissions**. At the end of the simulation, journal may export any or all of these lists as CSV files for further analysis.

Journal parameters are in general less elaborate than other modules and are divided into two main sections, [Selection Strategy](selection-strategies.md) and [Meta Analysis](meta_analyses.md).

- **`max_pubs`**, *`double`*, Maximum number of publications that is going to be accepted by the `Journal`.
- **`selection_strategy`**, *`string`*, The `SelectionStrategy` of the journal. See [Selection Strategy](selection-strategies.md)
- **`meta_analysis_metrics`**, *`list`*, List of meta analyses with their parameters. See [Meta Analysis](meta-analyses.md)


!!! journal "Journal's Configurations"
	```json
	    "journal_parameters": {
        "max_pubs": 24,
        "selection_strategy": {
            "name": "SignificantSelection",
            "alpha": 0.005,
            "pub_bias": 0.2,
            "side": 0
        },
        "meta_analysis_metrics": [
	        {
	            "name": "FixedEffectEstimator"
	        },
	        {
	            "name": "RandomEffectEstimator",
	            "estimator": "DL"
	        },
	        {
	            "name": "EggersTestEstimator",
	            "alpha": 0.1
	        }
	    ]
	```