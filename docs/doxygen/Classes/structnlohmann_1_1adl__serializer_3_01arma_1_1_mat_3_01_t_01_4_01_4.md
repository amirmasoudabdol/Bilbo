---
title: nlohmann::adl_serializer< arma::Mat< T > >


---

# nlohmann::adl_serializer< arma::Mat< T > >




 [More...](#detailed-description)















## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[to_json](/doxygen/Classes/structnlohmann_1_1adl__serializer_3_01arma_1_1_mat_3_01_t_01_4_01_4/#function-to_json)**(json & j, const arma::Mat< T > & mat)  |
| void | **[from_json](/doxygen/Classes/structnlohmann_1_1adl__serializer_3_01arma_1_1_mat_3_01_t_01_4_01_4/#function-from_json)**(const json & j, arma::Mat< T > & mat)  |








## Detailed Description

```cpp
template <typename T >
struct nlohmann::adl_serializer< arma::Mat< T > >;
```




































## Public Functions Documentation

### function to_json

```cpp
static inline void to_json(
    json & j,
    const arma::Mat< T > & mat
)
```





























### function from_json

```cpp
static inline void from_json(
    const json & j,
    arma::Mat< T > & mat
)
```



































-------------------------------

Updated on 22 November 2020 at 21:10:19 CET