---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# N-uplas `pair<A,B>` `tuple<...>`

**`pair<A, B>`:** Par de dois valores; suporta comparação lexicográfica.

**`tuple<A, B, C, ...>`:** Generalização do pair para N valores.

**Quando usar?** Agrupar valores sem criar struct; retornar múltiplos valores; ordenar por critério composto.

| | Acesso |
|---|---|
| `pair` | `.first`, `.second` |
| `tuple` | `get<i>(t)` |
| $\text{C++17}$ | `auto [a, b] = p` |

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
pair<int, int> p = {3, 7};
cout << p.first;   // 3
cout << p.second;  // 7

// Comparação lexicográfica
pair<int,int> a = {1, 5}, b = {1, 3};
cout << (a > b);   // true (1==1, então 5>3)

// Ordenar por segundo elemento
vector<pair<int,int>> v = {{1,3},{2,1},{0,2}};
sort(v.begin(), v.end()); // ordena pelo .first

// tuple
tuple<int, string, double> t = {1, "abc", 3.14};
cout << get<0>(t); // 1
cout << get<1>(t); // abc

// Structured bindings (C++17)
auto [x, y] = p;
auto [id, nome, nota] = t;
```

</div>
