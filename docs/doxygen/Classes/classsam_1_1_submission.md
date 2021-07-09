---
title: sam::Submission

---

# sam::Submission



## Public Functions

|                | Name           |
| -------------- | -------------- |
| bool | **[isSig](/doxygen/Classes/classsam_1_1_submission/#function-issig)**() const |
| bool | **[isHacked](/doxygen/Classes/classsam_1_1_submission/#function-ishacked)**() const |
| bool | **[isCandidate](/doxygen/Classes/classsam_1_1_submission/#function-iscandidate)**() const |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_submission/#function-columns)**()<br>Somewhat of a buffer for storing and returning a csv rows.  |
| | **[Submission](/doxygen/Classes/classsam_1_1_submission/#function-submission)**() =default |
| | **[Submission](/doxygen/Classes/classsam_1_1_submission/#function-submission)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & e, const int & index) |
| | **[Submission](/doxygen/Classes/classsam_1_1_submission/#function-submission)**(int sim_id, int expr_id, int rep_id, int pub_id, [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) dv) |
| | **[~Submission](/doxygen/Classes/classsam_1_1_submission/#function-~submission)**() =default |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| int | **[simid](/doxygen/Classes/classsam_1_1_submission/#variable-simid)** <br>Simulation ID.  |
| int | **[exprid](/doxygen/Classes/classsam_1_1_submission/#variable-exprid)** <br>[Experiment](/doxygen/Classes/classsam_1_1_experiment/) ID.  |
| int | **[repid](/doxygen/Classes/classsam_1_1_submission/#variable-repid)** <br>Replication ID.  |
| int | **[pubid](/doxygen/Classes/classsam_1_1_submission/#variable-pubid)** <br>Publication ID.  |
| [DependentVariable](/doxygen/Classes/classsam_1_1_dependent_variable/) | **[dv_](/doxygen/Classes/classsam_1_1_submission/#variable-dv_)**  |

## Public Functions Documentation

### function isSig

```cpp
inline bool isSig() const
```


### function isHacked

```cpp
inline bool isHacked() const
```


### function isCandidate

```cpp
inline bool isCandidate() const
```


### function Columns

```cpp
static std::vector< std::string > Columns()
```

Somewhat of a buffer for storing and returning a csv rows. 

### function Submission

```cpp
Submission() =default
```


### function Submission

```cpp
Submission(
    Experiment & e,
    const int & index
)
```


### function Submission

```cpp
Submission(
    int sim_id,
    int expr_id,
    int rep_id,
    int pub_id,
    DependentVariable dv
)
```


### function ~Submission

```cpp
~Submission() =default
```


## Public Attributes Documentation

### variable simid

```cpp
int simid {0};
```

Simulation ID. 

### variable exprid

```cpp
int exprid {0};
```

[Experiment](/doxygen/Classes/classsam_1_1_experiment/) ID. 

### variable repid

```cpp
int repid {0};
```

Replication ID. 

### variable pubid

```cpp
int pubid {0};
```

Publication ID. 

### variable dv_

```cpp
DependentVariable dv_;
```


-------------------------------

Updated on 29 June 2021 at 16:13:47 CEST