# Selective Reporting

Selective reporting is among the most prevalent questionable research practices [cite, cite]. It also sits high in the list of defensible QRPs among researchers [cite]. Despite its popularity and prevalent, it has been shown and argued that it has a devastating effect on our research. It gives the researcher a path to select any dependent variables from any treatment group, and present it as the primary outcome. This often allows the researcher to experiment with outcome variables and choose the *satisfactory* — e.g., significant — outcome variable.

As selective reporting often mainly induced in research in the form of a decision, SAM models this specific hacking strategy using the decision strategy. While the description of [decision strategy](decision-strategy.md) and [research workflow](research-workflow.md) should already be sufficient enough for the reader on how this method is being deployed in SAM, we use this section to elaborate on the implementation and implication of selective reporting.

## Selective Reporting as a Hacking Strategy

Unlike other hacking strategies, selective reporting is not being included in the list of `hacking_strategies` in the configuration file. Instead, we utilize different **selection → decision** sequences to simulate selective reporting. 

While most simulation studies apply the selective reporting in the beginning or at the end of the study, SAM is able to induce the selective reporting during any of the [decision stages](decision-strategy.md). In fact, any of `_selection_policies` listed in Figure 1 can be used to divert researchers selection from the pre-registered or primary outcome of the study. 

The simplest and most prominent way of alternating researchers selection is by configuring `initial_selection_policies`. Here we can lead the researcher to select an outcome with minimum *p*-value:

```
“initial_selection_policies”: [[“min(pvalue)”]]
```

Or, maybe we want to design a researcher who first checks the significance of the pre-registered outcome, and in the case of not being significant then selects an outcome with minimum *p*-value:

```
“initial_selection_policies”: [[“pre-reg”, “sig”], [“min(pvalue)”]]
```

As discussed, `initial_selection_policies` is a [policy chain set](decision-strategy.md#policy-chain-set), which means its policies will be executed in the given order, and researcher stops after a successful execution of a policy chain, ie., a query with an unique outcome.

## Selective Reporting Reach

Implementation of selective reporting through decision strategies opens a lot of opportunities for the researcher to selectively report different outcomes than those he/she pre-registered. Looking back at the list of possible selections, we will have 

- **→ `initial_selection_policies`**
- `will_start_hacking_decision_policies`
    - `stashing_policy`
    - **→ `h_s_selection`**
    - `h_s_decision`
    - ...
- **→ `between_hacks_selection_policies`**
- **→ `between_replications_selection_policies`**
- `will_continue_replicating_decision_policy`
- **→ `submission_decision_policies`**

Basically, Researcher can adjust his selection during the study. Keeping in mind that each selection policy is a [policy chain set](decision-strategy.md#policy-chain-set) means that Researcher can chain all his previous selection together and deploy a highly questionable selection scheme, and even adjust it through his/her research. For instance, Researcher’s selections could always start with checking the pre-registered outcome first, and only moves to other options when that one is not satisfactory.

```json
{
	“initial_selection_policies”: [[“pre-reg”, “sig”], [“min(pvalue)”]],
	“between_hacks_selection_policies”: [[“pre-reg”, “sig”], [“effect > 0”, “min(pvalue)”], [“effect < 0”, “max(pvalue)”],
	“between_replications_selection_policies”:[[“pre-reg”, “sig”], [“effect > 0”, “min(pvalue)”], [“sig”, “min(pvalue)”]]
}
```

Notice Researcher’s persistent on checking the `pre-reg` outcome in all different selection stages, and only accepting it when it is significant. This likely leads to an exceptionally hard to detect selective reporting. 

Moreover, as previously discussed, each hacking strategy get to have their own set of selection policies. This means we can specifically tune a hacking strategy to achieve a certain goal; therefore, incorporating selective reporting into each hacking strategy and the entire [hacking workflow](decision-strategey.md#hacking-workflow).
