---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Biblioteca Padrão (STL)

A STL é uma coleção de estruturas de dados e algoritmos prontos, testados e eficientes. Usá-la economiza tempo e evita erros.

Você pode importá-la completamente usando:

```cpp
#include <bits/stdc++.h>
```

Em juízes de CP isso está sempre disponível. Em produção, prefira incluir apenas os headers necessários.

::right::

**Containers** — estruturas de dados prontas:

- `vector`, `string`, `array`
- `stack`, `queue`, `deque`
- `set`, `multiset`
- `map`, `unordered_map`
- `priority_queue`

**Algoritmos** — funções sobre containers:

- `sort`, `reverse`, `unique`
- `lower_bound`, `upper_bound`, `binary_search`
- `min`, `max`, `min_element`, `max_element`
- `count`, `find`, `next_permutation`
