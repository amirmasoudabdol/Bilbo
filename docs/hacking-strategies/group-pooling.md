Group Pooling
-------------

Group pooling is the act of pooling data from two or more groups into one *new* group and compare the newly formed treatment group with the control group. Group pooling can be applied by adding the following JSON object to the list of hacking methods.

```json
{
  "name": "Group Pooling",
  "num": 2
}
```

Group pooling algorithm can pool different number of groups, `num`, together in order to form a new group. In its current setup, the Researcher traverses through every permutation of length `num` and create a new group. When, s/he collected all the combinations, s/he will then ask the `DecisionStrategy` for its `verdict` and consequently checks the significance of every new group.


| **Parameters** | **Type** | **Details**                                          |
|:---------------|:---------|:-----------------------------------------------------|
| `num`          | `int`    | Indicates the number of groups to be pooled together |
