---
title: nlohmann::adl_serializer< arma::Col< T > >


---

# nlohmann::adl_serializer< arma::Col< T > >




 [More...](#detailed-description)















## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[to_json](/doxygen/Classes/structnlohmann_1_1adl__serializer_3_01arma_1_1_col_3_01_t_01_4_01_4/#function-to_json)**(json & j, const arma::Col< T > & col)  |
| void | **[from_json](/doxygen/Classes/structnlohmann_1_1adl__serializer_3_01arma_1_1_col_3_01_t_01_4_01_4/#function-from_json)**(const json & j, arma::Col< T > & col)  |








## Detailed Description

```cpp
template <typename T >
struct nlohmann::adl_serializer< arma::Col< T > >;
```




































## Public Functions Documentation

### function to_json

```cpp
static inline void to_json(
    json & j,
    const arma::Col< T > & col
)
```





























### function from_json

```cpp
static inline void from_json(
    const json & j,
    arma::Col< T > & col
)
```



































-------------------------------

Updated on 22 November 2020 at 21:10:19 CET