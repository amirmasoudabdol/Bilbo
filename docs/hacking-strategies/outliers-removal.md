# Outliers Removal

Removing outliers is an important degree of freedom in the list degrees of freedom available to a researcher. While usage of outliers removal methods are not fully condemned [cite] and they are not strictly listed as questionable researcher practices [cite], they should not be applied blindly. Remisful application of these methods could disturb the observed effect size, and influence the significant level.

Unfortunately, most researchers are not aware of consequences of these methods, and as shown by [cite, cite], outliers removal methods are being applied recklessly without taking their influences into the consideration and only to achieve significance level, or removing “unwanted” observations [cite].

As mentioned, there is a range of methods and approaches available to remove outliers from an Experiment, each having their own strength and weakness [cite, cite, cite]. In its simplest form, outliers removal is done by calculating the relative distances of observations from the sample mean, $d_i = \frac{x_i - \bar{x}}{\sigma^2}$, and deciding whether to call an observation an outlier based on a pre-selected threshold, *k*. In this case, items further than *k* are considered outliers.

![<b>Figure 1.</b> Outliers Removal Algorithm](/hacking-strategies/figures/outlier-removal.png)

Figure 1 shows the implementation of aforementioned method. Like [optional stopping], outliers removal algorithm is designed based on the idea that Researchers might give the procedure several attempts before stop trying, `n_attempts`. Beside the number of attempts, we are able to provide a range of multipliers, *k*’s to be considered. At each iteration, we start by a *k*, and remove `num` observations from *targeted* groups. This routine will run `n_attemtps` times or at any time where `stopping_condition` is satisfied.

The configuration below showcases a sample implementation of outliers removal:

!!! hackingstrategy "Outlier Removal"
	```json
	{
	  "name": "Outlier Removal",
	  "num": 2,
	  "n_attempts": 3,
	  "min_observations": 20,
	  "multipliers": [3, 2, 1]
	}
	```
Besides hacking strategies shared parameters, outliers removal has its own customization parameters as follow:

- `num`, *n*, `int`, indicates number of items to be moved at each attempt
- `n_attempts`, indicates number of attempts to move outliers for ch multiplier
- `min_observations`, indicates the minimum number of servations. Outliers removal stops removing observations when a group reaches the given minimum.
- `multipliers`, indicates a list of multipliers to be used
- `order`, indicates the order in which observations will be removed from Experiment
	- `”random”`, removing items randomly
	- `”asc”`, removing furthest items from$\bar{x}$ first
	- `”desc”`, removing closest items to$\bar{x}$ first

\bibliography