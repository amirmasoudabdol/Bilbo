# Research Workflow

After [introducing](flow.md) general steps of conducting a research, in this section, we will get into the details of Decision Strategy and Research Workflow.

Figure 1 combines all the previously discussed processes and flowcharts in the [Flow](flow.md) sections, and gives an overview of the entire research workflow. The diagram can be separated into two main processes, *Main Research Line* and *Hacking Workflow*. Additionally, there are several *Selection→Decision* sequences spread throughout the flowchart (highlighted in red) that helps the researcher navigate between stages, and make certain decision, as briefly discussed in [Decision Strategy](design.md#decision-strategy).

![<b>Figure 1.</b> Overview of Research and Hacking Workflow. Colors represented in the figure are corresponding with those in Fig 1 of the Design section.](/figures/research-workflow.png)

This section will walk you through the above digram and discuss each steps in more details.


## Initial Stage


<picture>
  <img src="/figures/research-workflow-initial-stage.png" width="30%" align="right">
</picture>

As discussed in the [Introduction](/introduction.md), a research starts by initializing the Experiment Setup and thereafter preparation of the Experiment which consists of generating data, calculating statistics, running tests, calculating effects, etc.

When the Experiment is fully initialized, a Researcher can asses the quality of results, and select her preferred outcome among all available outcome variables across all conditions and dependent variables. This is being performed at the first selection step, **Initial Selection**. At this stage, Researcher can query all available outcomes using specific set of rules. For example, by using `["sig", "min(pvalue)"]` [Policy](/decision-strategies.md#policies) she would select an outcome with minimum *p*-value between those that are significant, or `["pre-reg"]` Policy results in selecting the pre-registered outcome. 

If the selection process is successful, Researcher continues to evaluate his submission, by *deciding* whether she is going to perform any QRP methods. This is being done at **Will be Hacking Decision** stage, where Researcher uses a [chain of policies](/decision-strategies.md#policies#policy-chains) to determine her next step. For instance, if she is looking for an outcome with positive effect (ie., `["effect > 0"]`) and the previously selected outcome does not have a positive effect, researcher might opt-in for applying some of the hacking strategies. 


## Hacking Workflow

<picture>
  <img src="/figures/research-workflow-hacking-workflow.png" width="55%" align="right">
</picture>

If Researcher is not satisfied with the selected submission, *and* the configuration indicates that he is going to apply some QRPs, then, he continues to the Hacking Workflow stage. 

In this stage, Researcher selects the first hacking strategy from his list, **H₁** and applies it on the Experiment. This process is highlighted in light blue, **Hack Experiment using Hᵢ**. After each QRP, researcher has a chance to collect the altered results for later investigation, we refer to this process as Stashing.

Whether the researcher performs a stashing process, or not, he will continues to another sequence of **Selection→Decision** where he evaluates the altered Experiment after applying H₁. The selection procedure is defined by another [set of policy chains](/decision-strategies.md#policies#policy-chain-sets) — **After Hacking Selection** — which leads either to an empty submission or an unique submission. Right after selection, researcher needs to *decide* whether he is going to continue the hacking procedure, or not — **Will Continue Hacking Decision.** 

If researcher decides to continue the hacking procedure, he would then choose the next hacking strategy, **H**, and repeat the same process. 

### Stashing and Post-QRP Selection

After leaving the Hacking Workflow, researcher is equipped with a set of outcomes selected from his ventures into his QRP arsenal. [Stashing policy](/decision-strategies.md#stashing-policy) indicates what sort of outcomes researcher is going to be collected by him after each hacking stagey. 

Researcher is being given the chance to select an outcome from his stashed outcome, **Hacked Outcomes DB.**, if he finds it necessary. In a real world scenario, this process mimic a very greedy and inconsiderate researcher who is trying everything to achieve a certain goal, ie., significance (`["sig"]`).


## Post-QRP Decision and Replication Stage

<picture>
  <img src="/figures/research-workflow-post-hacking-and-replication-stage.png" width="55%" align="right">
</picture>

Researcher's final selected outcome, S<sub>Fᵢ</sub> will be stored in another dataset, **Rep. Outcomes DB.**

If researcher is intending to perform more than one replication of his research, `n_reps`, see [configuration file](configuration-file.md#experiment-parameters). Then, he faces another decision, **Will Continue Replication Decision**. If the verdict is a yes, researcher stores current experiment's outcome, S<sub>Fᵢ</sub>, and initiates a replication of the Experiment using the parameters defined in Experiment Setup.

After performing `n_reps` replication, or negative ruling of **Will Continue Replicating Decision** researcher moves to the final stage of his research.

Throughout another **Selection→Decision** sequence, researcher select an outcome among all those stored from every replications, and decide whether he is going to submit that submission to Journal for review. The final decision stage acts as researcher's final call to whether his research is good enough (in his terms) to be submitted as a manuscript to the Journal.

## Finally

By the time that Final Submission, S<sub>F</sub>, is out of Researcher's hand and at Journal's stake, the process of  conducting research by Researcher is finalized. [Journal](/journal.md) will decide whether the manuscript is publishable or not, and SAM initiates a new Experiment Setup for starting a new Experiment, and consequently Researcher will conduct an entirely new research.