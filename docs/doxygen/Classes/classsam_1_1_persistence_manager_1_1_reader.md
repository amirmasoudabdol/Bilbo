---
title: sam::PersistenceManager::Reader

---

# sam::PersistenceManager::Reader



## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Reader](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_reader/#function-reader)**() =default |
| | **[~Reader](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_reader/#function-~reader)**() |
| | **[Reader](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_reader/#function-reader)**(const std::filesystem::path & filename) |
| void | **[filename](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_reader/#function-filename)**(const std::filesystem::path & name) |
| void | **[read_raw_data](/doxygen/Classes/classsam_1_1_persistence_manager_1_1_reader/#function-read_raw_data)**([Experiment](/doxygen/Classes/classsam_1_1_experiment/) * expr) |

## Public Functions Documentation

### function Reader

```cpp
Reader() =default
```


### function ~Reader

```cpp
~Reader()
```


### function Reader

```cpp
Reader(
    const std::filesystem::path & filename
)
```


### function filename

```cpp
inline void filename(
    const std::filesystem::path & name
)
```


### function read_raw_data

```cpp
void read_raw_data(
    Experiment * expr
)
```


-------------------------------

Updated on 29 June 2021 at 16:13:46 CEST