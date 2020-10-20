# Selective Reporting

Selective reporting is among the most prominent questionable research practices [cite, cite]. It is also among the methods with highest defensibility. However, it has been argued that it has a devastating effect on our research. It gives the researcher a path to select any dependent variables from any treatment group, and present it as the primary outcome. Even if it is not as apparent as discussed, it often allows the researcher to experiment with outcome variables and choose the *satisfactory* — e.g., significant — outcome variable.

As selective reporting often mainly induced in research in the form of a decision, SAM models this specific hacking strategy using the decision strategy. While the description of [decision strategy](decision-strategy.md) and [research workflow](research-workflow.md) should already be sufficient enough for the reader on how this method is being deployed in SAM, we use this section to elaborate on the implementation and implication of selective reporting.

## Selective Reporting as a Hacking Strategy

Unlike other hacking strategies, selective reporting is not being included in the list of `hacking_strategies` in the configuration file. Instead, we utilize different **selection → decision** sequences to simulate selective reporting. 

While most simulation studies apply the selective reporting in the beginning or at the end of the study, SAM is able to induce the selective reporting during any of the [decision stages](decision-strategy.md). In fact, any of `_selection_policies` listed in Figure 1 can be used to divert researchers selection from the pre-registered or primary outcome of the study. 

The simplest and most prominent way of alternating researchers selection is by configuring `initial_selection_policies`. Here we can lead the researcher to select an outcome with minimum *p*value:

```
	“initial_selection_policies”: [[“min(pvalue)”]]
```

Or, maybe we want to design a researcher who first checks the significance of the pre-registered outcome, and in the case of not being significant then selects an outcome with minimum *p*-values:

```
	“initial_selection_policies”: [[“pre-reg”, “sig”], [“min(pvalue)”]]
```

As discussed, `initial_selection_policies` is a [policy chain set](decision-strategy.md#policy-chain-set), which means its policies will be executed from first to last, and researcher will stop after a successful execution of a policy chain, ie., a query with an unique outcome.