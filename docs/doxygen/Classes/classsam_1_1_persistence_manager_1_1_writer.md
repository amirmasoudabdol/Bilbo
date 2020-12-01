---
title: sam::PersistenceManager::Writer
summary: Declration of the Writer class.  

---

# sam::PersistenceManager::Writer




Declration of the [Writer]() class. 

`#include <PersistenceManager.h>`













## Public Functions

|                | Name           |
| -------------- | -------------- |
|  | **[Writer](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/#function-writer)**() =default  |
|  | **[~Writer](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/#function-~writer)**()  |
|  | **[Writer](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/#function-writer)**(const string & filename)  |
|  | **[Writer](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/#function-writer)**(const string & path, const string & prefix, const string filename)  |
|  | **[Writer](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/#function-writer)**(const string & filename, const std::vector< std::string > colnames)  |
| void | **[write](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/#function-write)**(const std::vector< std::string > & row_entries)  |
| void | **[write](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/#function-write)**(const std::map< string, string > & row)  |
| void | **[write](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/#function-write)**(const [Submission](/doxygen/Classes/classsam_1_1_submission/) & sub)  |
| void | **[write](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/#function-write)**(std::vector< [Submission](/doxygen/Classes/classsam_1_1_submission/) > & subs, int sid =0)  |
| void | **[write](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/#function-write)**(std::vector< arma::Row< double >> & data, int sid =0)  |
| void | **[write](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/#function-write)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * experiment, string_view mode, int sid)  |
| void | **[setColumnNames](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_writer/#function-setcolumnnames)**(const std::vector< std::string > & colnames)  |
















## Public Functions Documentation

### function Writer

```cpp
Writer() =default
```





























### function ~Writer

```cpp
~Writer()
```





























### function Writer

```cpp
Writer(
    const string & filename
)
```





























### function Writer

```cpp
Writer(
    const string & path,
    const string & prefix,
    const string filename
)
```





























### function Writer

```cpp
Writer(
    const string & filename,
    const std::vector< std::string > colnames
)
```





























### function write

```cpp
void write(
    const std::vector< std::string > & row_entries
)
```





























### function write

```cpp
void write(
    const std::map< string, string > & row
)
```





























### function write

```cpp
void write(
    const Submission & sub
)
```





























### function write

```cpp
void write(
    std::vector< Submission > & subs,
    int sid =0
)
```


**Parameters**: 

  * **subs** A reference to [Submission](/doxygen/Classes/classsam_1_1_submission/) container 


























Write a list of submission records to a file, or a database 


### function write

```cpp
void write(
    std::vector< arma::Row< double >> & data,
    int sid =0
)
```


**Parameters**: 

  * **data** A reference to the Experiment->measurements 


























Write each groups' data to a file, or a database 


### function write

```cpp
void write(
    Experiment * experiment,
    string_view mode,
    int sid
)
```


**Parameters**: 

  * **A** constance reference to the [Experiment](/doxygen/Classes/classsam_1_1_experiment/)


























Write part of the [Experiment](/doxygen/Classes/classsam_1_1_experiment/) to a file, or a database 


### function setColumnNames

```cpp
void setColumnNames(
    const std::vector< std::string > & colnames
)
```



































-------------------------------

Updated on 23 November 2020 at 14:03:43 CET