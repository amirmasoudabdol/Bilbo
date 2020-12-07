---
title: sam::Journal


---

# sam::Journal











## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Parameters](/doxygen/Classes/structsam_1_1_journal_1_1_parameters/)**  |








## Public Functions

|                | Name           |
| -------------- | -------------- |
| std::vector< std::string > | **[Columns](/doxygen/Classes/classsam_1_1_journal/#function-columns)**()  |
|  | **[operator arma::Row< double >](/doxygen/Classes/classsam_1_1_journal/#function-operator-armarow<-double->)**()  |
|  | **[Journal](/doxygen/Classes/classsam_1_1_journal/#function-journal)**() =default  |
|  | **[~Journal](/doxygen/Classes/classsam_1_1_journal/#function-~journal)**() =default  |
|  | **[Journal](/doxygen/Classes/classsam_1_1_journal/#function-journal)**(json & journal_config)  |
|  | **[Journal](/doxygen/Classes/classsam_1_1_journal/#function-journal)**(const [Parameters](/doxygen/Classes/structsam_1_1_journal_1_1_parameters/) & jp)  |
| void | **[setSelectionStrategy](/doxygen/Classes/classsam_1_1_journal/#function-setselectionstrategy)**(std::unique_ptr< SelectionStrategy > ss)  |
| bool | **[review](/doxygen/Classes/classsam_1_1_journal/#function-review)**([Submission](/doxygen/Classes/classsam_1_1_submission/) & s) <br>Review the [Submission]() by calling `SelectionStrategy::review()`.  |
| void | **[accept](/doxygen/Classes/classsam_1_1_journal/#function-accept)**(const [Submission](/doxygen/Classes/classsam_1_1_submission/) & s) <br>Accept the [Submission]() by adding it to the `publicationList`.  |
| void | **[reject](/doxygen/Classes/classsam_1_1_journal/#function-reject)**(const [Submission](/doxygen/Classes/classsam_1_1_submission/) & s) <br>Rejecting the Submission!  |
| bool | **[isStillAccepting](/doxygen/Classes/classsam_1_1_journal/#function-isstillaccepting)**() const  |
| void | **[saveSubmissions](/doxygen/Classes/classsam_1_1_journal/#function-savesubmissions)**(int simid, std::ofstream & writer)  |
| void | **[saveMetaAnalysis](/doxygen/Classes/classsam_1_1_journal/#function-savemetaanalysis)**()  |
| void | **[saveSummaries](/doxygen/Classes/classsam_1_1_journal/#function-savesummaries)**()  |
| void | **[saveMetaStatsOf](/doxygen/Classes/classsam_1_1_journal/#function-savemetastatsof)**(std::string method)  |
| void | **[savePulicationsPerSimSummaries](/doxygen/Classes/classsam_1_1_journal/#function-savepulicationspersimsummaries)**() <br>Saving the runner statistics of each batch of publications in [Journal](/doxygen/Classes/classsam_1_1_journal/).  |
| void | **[clear](/doxygen/Classes/classsam_1_1_journal/#function-clear)**()  |
| void | **[prepareForMetaAnalysis](/doxygen/Classes/classsam_1_1_journal/#function-prepareformetaanalysis)**()  |
| void | **[runMetaAnalysis](/doxygen/Classes/classsam_1_1_journal/#function-runmetaanalysis)**()  |
| void | **[updateTheOverallRunner](/doxygen/Classes/classsam_1_1_journal/#function-updatetheoverallrunner)**()  |


## Public Attributes

|                | Name           |
| -------------- | -------------- |
| double | **[max_pubs](/doxygen/Classes/classsam_1_1_journal/#variable-max_pubs)**  |
| std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > | **[publications_list](/doxygen/Classes/classsam_1_1_journal/#variable-publications_list)** <br>List of all accepted Submissions, i.e., publications.  |
| int | **[n_accepted](/doxygen/Classes/classsam_1_1_journal/#variable-n_accepted)**  |
| std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > | **[rejection_list](/doxygen/Classes/classsam_1_1_journal/#variable-rejection_list)** <br>Rejected Submissions.  |
| int | **[n_rejected](/doxygen/Classes/classsam_1_1_journal/#variable-n_rejected)**  |
| int | **[n_sigs](/doxygen/Classes/classsam_1_1_journal/#variable-n_sigs)** <br>Number of significant submissions.  |
| double | **[sum_sig_pvalue](/doxygen/Classes/classsam_1_1_journal/#variable-sum_sig_pvalue)**  |
| double | **[mean_sig_pvalue](/doxygen/Classes/classsam_1_1_journal/#variable-mean_sig_pvalue)**  |
| double | **[sum_sig_effect](/doxygen/Classes/classsam_1_1_journal/#variable-sum_sig_effect)**  |
| double | **[mean_sig_effect](/doxygen/Classes/classsam_1_1_journal/#variable-mean_sig_effect)**  |
| arma::Row< double > | **[yi](/doxygen/Classes/classsam_1_1_journal/#variable-yi)** <br>Caching variables.  |
| arma::Row< double > | **[vi](/doxygen/Classes/classsam_1_1_journal/#variable-vi)**  |
| arma::Row< double > | **[wi](/doxygen/Classes/classsam_1_1_journal/#variable-wi)**  |
| bool | **[is_saving_summaries](/doxygen/Classes/classsam_1_1_journal/#variable-is_saving_summaries)**  |
| bool | **[is_saving_meta](/doxygen/Classes/classsam_1_1_journal/#variable-is_saving_meta)**  |
| bool | **[is_saving_pubs_per_sim_summaries](/doxygen/Classes/classsam_1_1_journal/#variable-is_saving_pubs_per_sim_summaries)**  |
| arma::running_stat_vec< arma::Row< double > > | **[pubs_per_sim_stat_runner](/doxygen/Classes/classsam_1_1_journal/#variable-pubs_per_sim_stat_runner)**  |
| std::unique_ptr< [PersistenceManager::Writer](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/) > | **[pubs_per_sim_stats_writer](/doxygen/Classes/classsam_1_1_journal/#variable-pubs_per_sim_stats_writer)**  |
| arma::running_stat_vec< arma::Row< double > > | **[pubs_stat_runner](/doxygen/Classes/classsam_1_1_journal/#variable-pubs_stat_runner)**  |
| std::unique_ptr< [PersistenceManager::Writer](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/) > | **[pubs_stats_writer](/doxygen/Classes/classsam_1_1_journal/#variable-pubs_stats_writer)**  |
| std::unique_ptr< SelectionStrategy > | **[selection_strategy](/doxygen/Classes/classsam_1_1_journal/#variable-selection_strategy)** <br>[Journal](/doxygen/Classes/classsam_1_1_journal/)'s Selection Model/Strategy.  |
| std::map< std::string, std::vector< std::string > > | **[meta_columns](/doxygen/Classes/classsam_1_1_journal/#variable-meta_columns)** <br>Meta Analysis Estimators and their Stats Runner.  |
| std::map< std::string, std::vector< std::string > > | **[meta_stats_columns](/doxygen/Classes/classsam_1_1_journal/#variable-meta_stats_columns)**  |
| std::vector< std::unique_ptr< [MetaAnalysis](/doxygen/Classes/classsam_1_1_meta_analysis/) > > | **[meta_analysis_strategies](/doxygen/Classes/classsam_1_1_journal/#variable-meta_analysis_strategies)**  |
| std::map< std::string, arma::running_stat_vec< arma::Row< double > > > | **[meta_stat_runners](/doxygen/Classes/classsam_1_1_journal/#variable-meta_stat_runners)**  |
| std::map< std::string, [PersistenceManager::Writer](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/) > | **[meta_writers](/doxygen/Classes/classsam_1_1_journal/#variable-meta_writers)**  |
| std::map< std::string, [PersistenceManager::Writer](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/) > | **[meta_stats_writers](/doxygen/Classes/classsam_1_1_journal/#variable-meta_stats_writers)**  |
| std::vector< std::string > | **[submission_columns](/doxygen/Classes/classsam_1_1_journal/#variable-submission_columns)**  |
| std::vector< std::string > | **[stats_columns](/doxygen/Classes/classsam_1_1_journal/#variable-stats_columns)**  |
| MetaAnalysisResults | **[meta_analysis_submissions](/doxygen/Classes/classsam_1_1_journal/#variable-meta_analysis_submissions)**  |
| [Parameters](/doxygen/Classes/structsam_1_1_journal_1_1_parameters/) | **[params](/doxygen/Classes/classsam_1_1_journal/#variable-params)**  |














## Public Functions Documentation

### function Columns

```cpp
static std::vector< std::string > Columns()
```





























### function operator arma::Row< double >

```cpp
inline operator arma::Row< double >()
```





























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




























For each given method, we prepare their output columns names, and an output file. If we are saving summaries, we initialize a stats runner, as well as appropriate column names, and output file.

Removing the higher level information because I don't want them to be written to the config file again.

### function Journal

```cpp
explicit Journal(
    const Parameters & jp
)
```





























### function setSelectionStrategy

```cpp
inline void setSelectionStrategy(
    std::unique_ptr< SelectionStrategy > ss
)
```


**Parameters**: 

  * **s** The pointer to the given selection strategy 


























Point [Journal](/doxygen/Classes/classsam_1_1_journal/)'s selection strategy to the given strategy


### function review

```cpp
bool review(
    Submission & s
)
```

Review the [Submission]() by calling `SelectionStrategy::review()`. 

**Parameters**: 

  * **s** A reference to the [Submission](/doxygen/Classes/classsam_1_1_submission/)







**Return**: A boolean indicating whether the [Submission](/doxygen/Classes/classsam_1_1_submission/) should be accpeted or not. 




















Stats runner over all publications of this journal

Stat runner over all simulations

### function accept

```cpp
void accept(
    const Submission & s
)
```

Accept the [Submission]() by adding it to the `publicationList`. 

**Parameters**: 

  * **s** A copy of the [Submission](/doxygen/Classes/classsam_1_1_submission/)



























TodoMaybe I should calculate the publications stats here 

Updating journal's info

Adding current info to the stat runner

### function reject

```cpp
void reject(
    const Submission & s
)
```

Rejecting the Submission! 

**Parameters**: 

  * **s** A reference to the [Submission](/doxygen/Classes/classsam_1_1_submission/)




























### function isStillAccepting

```cpp
inline bool isStillAccepting() const
```





























### function saveSubmissions

```cpp
void saveSubmissions(
    int simid,
    std::ofstream & writer
)
```


**Parameters**: 

  * **simid** The index to be used for the given set. 
  * **writer** The output file. 


























Save enteries of publications_list to a CSV file.


### function saveMetaAnalysis

```cpp
void saveMetaAnalysis()
```





























### function saveSummaries

```cpp
void saveSummaries()
```




























Preparing and writting the summary of every meta-analysis method

Preparing the summary of all publications

Preparing the summary of journal's info by adding it to the end of publication's record

### function saveMetaStatsOf

```cpp
void saveMetaStatsOf(
    std::string method
)
```





























### function savePulicationsPerSimSummaries

```cpp
void savePulicationsPerSimSummaries()
```

Saving the runner statistics of each batch of publications in [Journal](/doxygen/Classes/classsam_1_1_journal/). 



























Reseting the runner statistics

### function clear

```cpp
inline void clear()
```



























Clear the publications_list vector. 


### function prepareForMetaAnalysis

```cpp
inline void prepareForMetaAnalysis()
```





























### function runMetaAnalysis

```cpp
void runMetaAnalysis()
```





























### function updateTheOverallRunner

```cpp
void updateTheOverallRunner()
```































## Public Attributes Documentation

### variable max_pubs

```cpp
double max_pubs;
```





























### variable publications_list

```cpp
std::vector< Submission > publications_list;
```

List of all accepted Submissions, i.e., publications. 




























### variable n_accepted

```cpp
int n_accepted {0};
```





























### variable rejection_list

```cpp
std::vector< Submission > rejection_list;
```

Rejected Submissions. 




























### variable n_rejected

```cpp
int n_rejected {0};
```





























### variable n_sigs

```cpp
int n_sigs {0};
```

Number of significant submissions. 




























### variable sum_sig_pvalue

```cpp
double sum_sig_pvalue {0};
```





























### variable mean_sig_pvalue

```cpp
double mean_sig_pvalue {0};
```





























### variable sum_sig_effect

```cpp
double sum_sig_effect {0};
```





























### variable mean_sig_effect

```cpp
double mean_sig_effect {0};
```





























### variable yi

```cpp
arma::Row< double > yi;
```

Caching variables. 




























### variable vi

```cpp
arma::Row< double > vi;
```





























### variable wi

```cpp
arma::Row< double > wi;
```





























### variable is_saving_summaries

```cpp
bool is_saving_summaries;
```





























### variable is_saving_meta

```cpp
bool is_saving_meta;
```





























### variable is_saving_pubs_per_sim_summaries

```cpp
bool is_saving_pubs_per_sim_summaries;
```





























### variable pubs_per_sim_stat_runner

```cpp
arma::running_stat_vec< arma::Row< double > > pubs_per_sim_stat_runner;
```





























### variable pubs_per_sim_stats_writer

```cpp
std::unique_ptr< PersistenceManager::Writer > pubs_per_sim_stats_writer;
```





























### variable pubs_stat_runner

```cpp
arma::running_stat_vec< arma::Row< double > > pubs_stat_runner;
```





























### variable pubs_stats_writer

```cpp
std::unique_ptr< PersistenceManager::Writer > pubs_stats_writer;
```





























### variable selection_strategy

```cpp
std::unique_ptr< SelectionStrategy > selection_strategy;
```

[Journal](/doxygen/Classes/classsam_1_1_journal/)'s Selection Model/Strategy. 




























### variable meta_columns

```cpp
std::map< std::string, std::vector< std::string > > meta_columns;
```

Meta Analysis Estimators and their Stats Runner. 




























### variable meta_stats_columns

```cpp
std::map< std::string, std::vector< std::string > > meta_stats_columns;
```





























### variable meta_analysis_strategies

```cpp
std::vector< std::unique_ptr< MetaAnalysis > > meta_analysis_strategies;
```





























### variable meta_stat_runners

```cpp
std::map< std::string, arma::running_stat_vec< arma::Row< double > > > meta_stat_runners;
```





























### variable meta_writers

```cpp
std::map< std::string, PersistenceManager::Writer > meta_writers;
```





























### variable meta_stats_writers

```cpp
std::map< std::string, PersistenceManager::Writer > meta_stats_writers;
```





























### variable submission_columns

```cpp
std::vector< std::string > submission_columns;
```





























### variable stats_columns

```cpp
std::vector< std::string > stats_columns;
```





























### variable meta_analysis_submissions

```cpp
MetaAnalysisResults meta_analysis_submissions;
```





























### variable params

```cpp
Parameters params;
```

































-------------------------------

Updated on  7 December 2020 at 13:20:07 CET