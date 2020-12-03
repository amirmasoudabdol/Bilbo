---
title: sam::Submission


---

# sam::Submission



















## Public Functions

|                | Name           |
| -------------- | -------------- |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_submission/#function-columns)**()  |
|  | **[Submission](/doxygen/Classes/classsam_1_1_submission/#function-submission)**() =default  |
|  | **[Submission](/doxygen/Classes/classsam_1_1_submission/#function-submission)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) & e, const int & index)  |
|  | **[~Submission](/doxygen/Classes/classsam_1_1_submission/#function-~submission)**() =default  |
| bool | **[isSig](/doxygen/Classes/classsam_1_1_submission/#function-issig)**() const  |
|  | **[operator arma::Row< double >](/doxygen/Classes/classsam_1_1_submission/#function-operator-armarow<-double->)**()  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| int | **[simid](/doxygen/Classes/classsam_1_1_submission/#variable-simid)** <br>Simulation ID.  |
| int | **[exprid](/doxygen/Classes/classsam_1_1_submission/#variable-exprid)** <br>[Experiment](/doxygen/Classes/classsam_1_1_experiment/) ID.  |
| int | **[repid](/doxygen/Classes/classsam_1_1_submission/#variable-repid)** <br>Replicaiton ID.  |
| int | **[pubid](/doxygen/Classes/classsam_1_1_submission/#variable-pubid)** <br>Publication ID.  |
| int | **[tnobs](/doxygen/Classes/classsam_1_1_submission/#variable-tnobs)** <br>Index of the selected group.  |
| [Group](/doxygen/Classes/classsam_1_1_group/) | **[group_](/doxygen/Classes/classsam_1_1_submission/#variable-group_)**  |


## Friends

|                | Name           |
| -------------- | -------------- |
| OStream & | **[operator<<](/doxygen/Classes/classsam_1_1_submission/#friend-operator<<)**(OStream & os, const [Submission](/doxygen/Classes/classsam_1_1_submission/) & s)  |












## Public Functions Documentation

### function Columns

```cpp
static std::vector< std::string > Columns()
```





























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





























### function ~Submission

```cpp
~Submission() =default
```





























### function isSig

```cpp
inline bool isSig() const
```








**Return**: `true` if the [Submission](/doxygen/Classes/classsam_1_1_submission/) is significant, `false` otherwise 





















### function operator arma::Row< double >

```cpp
operator arma::Row< double >()
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

Replicaiton ID. 




























### variable pubid

```cpp
int pubid {0};
```

Publication ID. 




























### variable tnobs

```cpp
int tnobs;
```

Index of the selected group. 


























True number of observations 


### variable group_

```cpp
Group group_;
```































## Friends

### friend operator<<

```cpp
friend OStream & operator<<(
    OStream & os,
    const Submission & s
);
```































-------------------------------

Updated on  3 December 2020 at 12:37:28 CET