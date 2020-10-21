# Journal

At the end of the [research workflow](research-workflow.md), Researcher has either decided to discard his research, or, prepares to submit his final submission to the Journal. At this point, he passes his manuscript to Journal, and therefore will have no control over its destiny anymore. 

Journal module is designed to simulate the reviewing process. After receiving the submission (ie. Manuscript) from Researcher, Journal asses whether to accept or reject the submission. Journal’s assessment is being conducted using groups of pre-defined algorithm, or criteria. We are referring to these algorithms as *Selection Strategies*. 

![<b>Figure 1.</b> Journal’s Reviewing Workflow](journal-review-workflow.md)

Figure 1 shows the steps taken by Journal during the review process. Journal starts by querying the selection strategy for its verdict on whether the given submission is suitable for publication or not. For example, a selection strategy focused on simulating *publication bias* effect might based its decision on availability of positive significant effect, and therefore reject non-significant results 95% times (publication bias rate).

If selection strategy approves the “quality” of the submission, submission will be accepted and stored in a database of accepted outcomes, a.k.a, **publications list**. In contrast, rejected outcomes will not be published and stored in **rejected submissions**. At the end of the simulation, journal may export any or all of these lists as a CSV file for further analysis.

## Selection Strategies

