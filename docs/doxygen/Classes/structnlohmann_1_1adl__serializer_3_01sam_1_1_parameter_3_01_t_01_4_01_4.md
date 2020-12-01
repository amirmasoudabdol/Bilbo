---
title: nlohmann::adl_serializer< sam::Parameter< T > >


---

# nlohmann::adl_serializer< sam::Parameter< T > >




 [More...](#detailed-description)















## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[to_json](/doxygen/Classes/structnlohmann_1_1adl__serializer_3_01sam_1_1_parameter_3_01_t_01_4_01_4/#function-to_json)**(json & j, const [sam::Parameter](/doxygen/Classes/classsam_1_1_parameter/)< T > & p)  |
| void | **[from_json](/doxygen/Classes/structnlohmann_1_1adl__serializer_3_01sam_1_1_parameter_3_01_t_01_4_01_4/#function-from_json)**(const json & j, [sam::Parameter](/doxygen/Classes/classsam_1_1_parameter/)< T > & p)  |








## Detailed Description

```cpp
template <typename T >
struct nlohmann::adl_serializer< sam::Parameter< T > >;
```




































## Public Functions Documentation

### function to_json

```cpp
static inline void to_json(
    json & j,
    const sam::Parameter< T > & p
)
```





























### function from_json

```cpp
static inline void from_json(
    const json & j,
    sam::Parameter< T > & p
)
```



































-------------------------------

Updated on 22 November 2020 at 21:10:19 CET