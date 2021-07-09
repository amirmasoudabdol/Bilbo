---
title: sam::Journal
summary: Journal Class. 

---

# sam::Journal



[Journal]() Class.  [More...](#detailed-description)


`#include <Journal.h>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Journal](/doxygen/Classes/classsam_1_1_journal/#function-journal)**() =default |
| | **[~Journal](/doxygen/Classes/classsam_1_1_journal/#function-~journal)**() =default |
| | **[Journal](/doxygen/Classes/classsam_1_1_journal/#function-journal)**(json & journal_config)<br>Constructs a [Journal](/doxygen/Classes/classsam_1_1_journal/) from a JSON object.  |
| bool | **[review](/doxygen/Classes/classsam_1_1_journal/#function-review)**(std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & s)<br>Review the [Submission]().  |
| void | **[accept](/doxygen/Classes/classsam_1_1_journal/#function-accept)**(const std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & s)<br>Accepts the [Submission]().  |
| void | **[reject](/doxygen/Classes/classsam_1_1_journal/#function-reject)**(const std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & s)<br>Rejects the [Submission]().  |
| bool | **[isStillAccepting](/doxygen/Classes/classsam_1_1_journal/#function-isstillaccepting)**() const<br>Indicates whether the [Journal](/doxygen/Classes/classsam_1_1_journal/) is still accepting outcomes or not.  |
| size_t | **[nStudies](/doxygen/Classes/classsam_1_1_journal/#function-nstudies)**() const<br>Returns the number of studies.  |
| size_t | **[nSubmissions](/doxygen/Classes/classsam_1_1_journal/#function-nsubmissions)**() const<br>Returns the number of publications.  |
| size_t | **[nRejected](/doxygen/Classes/classsam_1_1_journal/#function-nrejected)**() const<br>Returns the number of rejected publications.  |
| void | **[saveMetaAnalysis](/doxygen/Classes/classsam_1_1_journal/#function-savemetaanalysis)**()<br>Saves [MetaAnalysis]() Results.  |
| void | **[saveSummaries](/doxygen/Classes/classsam_1_1_journal/#function-savesummaries)**()<br>Saves Overall Summaries.  |
| void | **[storeMetaAnalysisResult](/doxygen/Classes/classsam_1_1_journal/#function-storemetaanalysisresult)**(const [MetaAnalysisOutcome](/doxygen/Namespaces/namespacesam/#using-metaanalysisoutcome) & res)<br>Stores the MetaAnalysisOutcome.  |
| void | **[savePublicationsPerSimSummaries](/doxygen/Classes/classsam_1_1_journal/#function-savepublicationspersimsummaries)**()<br>Saves the Per Simulation summary of Publications.  |
| void | **[clear](/doxygen/Classes/classsam_1_1_journal/#function-clear)**()<br>Clear the [Journal](/doxygen/Classes/classsam_1_1_journal/).  |
| void | **[reset](/doxygen/Classes/classsam_1_1_journal/#function-reset)**()<br>Completely resets the [Journal](/doxygen/Classes/classsam_1_1_journal/).  |
| void | **[prepareForMetaAnalysis](/doxygen/Classes/classsam_1_1_journal/#function-prepareformetaanalysis)**()<br>Prepares the [Journal](/doxygen/Classes/classsam_1_1_journal/) for running meta-analysis.  |
| void | **[runMetaAnalysis](/doxygen/Classes/classsam_1_1_journal/#function-runmetaanalysis)**()<br>Runs the meta-analysis methods.  |
| void | **[updateMetaStatsRunners](/doxygen/Classes/classsam_1_1_journal/#function-updatemetastatsrunners)**()<br>Updates the overall stats runners.  |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_journal/#function-columns)**()<br>Returns [Journal](/doxygen/Classes/classsam_1_1_journal/)'s CSV header.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > | **[publications_list](/doxygen/Classes/classsam_1_1_journal/#variable-publications_list)** <br>List of all accepted submissions, i.e., outcomes.  |
| std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > | **[rejection_list](/doxygen/Classes/classsam_1_1_journal/#variable-rejection_list)** <br>Rejected Submissions.  |
| arma::Row< float > | **[yi](/doxygen/Classes/classsam_1_1_journal/#variable-yi)**  |
| arma::Row< float > | **[vi](/doxygen/Classes/classsam_1_1_journal/#variable-vi)** <br>The variance of the accepted submissions.  |
| arma::Row< float > | **[wi](/doxygen/Classes/classsam_1_1_journal/#variable-wi)** <br>The weight of the accepted submissions, computed as 1./vi;.  |
| std::unique_ptr< ReviewStrategy > | **[review_strategy](/doxygen/Classes/classsam_1_1_journal/#variable-review_strategy)** <br>[Journal](/doxygen/Classes/classsam_1_1_journal/)'s Selection Model/Strategy.  |

## Detailed Description

```cpp
class sam::Journal;
```

[Journal]() Class. 

The [Journal](/doxygen/Classes/classsam_1_1_journal/) class mimics the behavior of a [Journal](/doxygen/Classes/classsam_1_1_journal/). It deals with new publications as they are being submitted for review. It is equipped with a review strategy which is used to make a decision over the destiny of the newly submitted manuscript, ie., being accepted or rejected.

Additionally, it handles the meta-analysis calculation and reporting of those at the end of the simulation. 

## Public Functions Documentation

### function Journal

```cpp
Journal() =default
```


### function ~Journal

```cpp
~Journal() =default
```


### function Journal

```cpp
explicit Journal(
    json & journal_config
)
```

Constructs a [Journal](/doxygen/Classes/classsam_1_1_journal/) from a JSON object. 

**Parameters**: 

  * **journal_config** The journal configuration 


This makes sure that everything in the [Journal](/doxygen/Classes/classsam_1_1_journal/) are set up correctly:



* Instantiates the Review Strategy
* Prepares the output files, and their column names
* Prepares the stat runners based on users preference


Removing the higher level information because I don't want them to be written to the config file again.


### function review

```cpp
bool review(
    std::vector< Submission > & s
)
```

Review the [Submission](). 

**Parameters**: 

  * **subs** A list of submissions


**Return**: Returns `true` if the submission is accepted, otherwise it returns false. 

Sends the submission to the review strategy, and based on its verdict it either [accept()](/doxygen/Classes/classsam_1_1_journal/#function-accept) or [reject()](/doxygen/Classes/classsam_1_1_journal/#function-reject) the submission.


### function accept

```cpp
void accept(
    const std::vector< Submission > & s
)
```

Accepts the [Submission](). 

**Parameters**: 

  * **subs** A list of submissions 


Adds the accepted submission to the list of publications, and updates some of the necessary internals of the [Journal](/doxygen/Classes/classsam_1_1_journal/) to be able to keep track of the number of publications, studies, etc.


### function reject

```cpp
void reject(
    const std::vector< Submission > & s
)
```

Rejects the [Submission](). 

**Parameters**: 

  * **subs** A list of submissions 


Adds the rejected submissions to the list of rejected submissions, and keeps the internal of the [Journal](/doxygen/Classes/classsam_1_1_journal/) up-to-date.


### function isStillAccepting

```cpp
inline bool isStillAccepting() const
```

Indicates whether the [Journal](/doxygen/Classes/classsam_1_1_journal/) is still accepting outcomes or not. 

### function nStudies

```cpp
inline size_t nStudies() const
```

Returns the number of studies. 

### function nSubmissions

```cpp
inline size_t nSubmissions() const
```

Returns the number of publications. 

### function nRejected

```cpp
inline size_t nRejected() const
```

Returns the number of rejected publications. 

### function saveMetaAnalysis

```cpp
void saveMetaAnalysis()
```

Saves [MetaAnalysis]() Results. 

Saves the meta analytics results. 


### function saveSummaries

```cpp
void saveSummaries()
```

Saves Overall Summaries. 

Saves the publications and meta stats runners. 


### function storeMetaAnalysisResult

```cpp
void storeMetaAnalysisResult(
    const MetaAnalysisOutcome & res
)
```

Stores the MetaAnalysisOutcome. 

Adds the given meta analysis outcome to the list of collected meta-analysis. 


### function savePublicationsPerSimSummaries

```cpp
void savePublicationsPerSimSummaries()
```

Saves the Per Simulation summary of Publications. 

Saving the runner statistics of each batch of publications in [Journal](/doxygen/Classes/classsam_1_1_journal/). 


Resetting the runner statistics


### function clear

```cpp
void clear()
```

Clear the [Journal](/doxygen/Classes/classsam_1_1_journal/). 

Clears the history of publications, rejections, and runner statistics... 


### function reset

```cpp
void reset()
```

Completely resets the [Journal](/doxygen/Classes/classsam_1_1_journal/). 

In addition to clearing the [Journal](/doxygen/Classes/classsam_1_1_journal/), it resets some of the overall stats runners that are not usually being cleared by [clear()](/doxygen/Classes/classsam_1_1_journal/#function-clear)


### function prepareForMetaAnalysis

```cpp
void prepareForMetaAnalysis()
```

Prepares the [Journal](/doxygen/Classes/classsam_1_1_journal/) for running meta-analysis. 

This prepares the [Journal](/doxygen/Classes/classsam_1_1_journal/) for running meta-analysis. I mainly designed this to introduce some caching that I don't have to compute everything every time. So, with this, [Journal](/doxygen/Classes/classsam_1_1_journal/) prepares the [vi](/doxygen/Classes/classsam_1_1_journal/#variable-vi), [yi](/doxygen/Classes/classsam_1_1_journal/#variable-yi), and [wi](/doxygen/Classes/classsam_1_1_journal/#variable-wi) once and pass them to the meta analysis methods. 


### function runMetaAnalysis

```cpp
void runMetaAnalysis()
```

Runs the meta-analysis methods. 

Loops through the meta-analysis methods and run them, and update their stats runners 


### function updateMetaStatsRunners

```cpp
void updateMetaStatsRunners()
```

Updates the overall stats runners. 

Updates the overall meta stats runners. 


### function Columns

```cpp
static std::vector< std::string > Columns()
```

Returns [Journal](/doxygen/Classes/classsam_1_1_journal/)'s CSV header. 

## Public Attributes Documentation

### variable publications_list

```cpp
std::vector< Submission > publications_list;
```

List of all accepted submissions, i.e., outcomes. 

### variable rejection_list

```cpp
std::vector< Submission > rejection_list;
```

Rejected Submissions. 

### variable yi

```cpp
arma::Row< float > yi;
```


Caching variables The effect sizes of the accepted submissions. 


### variable vi

```cpp
arma::Row< float > vi;
```

The variance of the accepted submissions. 

### variable wi

```cpp
arma::Row< float > wi;
```

The weight of the accepted submissions, computed as 1./vi;. 

### variable review_strategy

```cpp
std::unique_ptr< ReviewStrategy > review_strategy;
```

[Journal](/doxygen/Classes/classsam_1_1_journal/)'s Selection Model/Strategy. 

-------------------------------

Updated on 29 June 2021 at 16:13:46 CEST