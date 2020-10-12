# Optional Stopping

Optional stopping is the practice of adding new observations to `Experiment`'s data after the initial data collection. The incentive behind applying this method is often to achieve significant results. A researcher can perform this method in many way. Here we have tried to provide a set of parameters that can collectively mimic as many scenarios as possible.

In order to add optional stopping to your list of hacking, you must replace one of the hacking methods, $h_i$ with the code block below.

```json
{
  "name": "Optional Stopping",
  "num": 3,
  "attempts": 3,
  "max attempts": 10,
  "level": "dv"
}
```

The optional stopping algorithm is implemented based on the fact that often a researcher performs multiple attempts to achieve significance. Here, `attempts` defines the number of attempts and `num` specifies the number of items --- to be added --- in each attempt.



| **Parameters** | **Type**         | **Description**                                |
|:---------------|:-----------------|:-----------------------------------------------|
| `num`          | *n*, `int` to at | Number of observations be added on each tempt. |
| `attempts`     | *t*, `int` be pr | Number of attempts fore stopping the ocess.    |
| `max_attempts` | *m*, `int` at    | Maximum number of tempts                       |
| "d             | vs" Ad de        | ding new values to pendent variables.          |

You can control the intensity of optional stopping by alternating the available parameters. For instance, you can implement an *extreme* optional stopping by setting `num = 1` and using large values for `attempts` and `max_attempts`.

!!! note

    As discussed in the `data-strategies`{.interpreted-text role="ref"}     section, optional stopping utilizes the `DataStrategy` for generating     new data points.
