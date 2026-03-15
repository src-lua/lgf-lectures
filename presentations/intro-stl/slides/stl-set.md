---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Conjuntos `set<T>`  `multiset<T>`

**`set<T>`:** Conjunto ordenado de elementos **únicos** (árvore rubro-negra internamente).

**`multiset<T>`:** Igual, mas permite elementos repetidos.

**Quando usar?** Manter elementos únicos e ordenados; verificar existência, inserir e remover em $O(\log N)$.

| Operação | Custo |
|---|---|
| `insert(x)` | $O(\log N)$ |
| `erase(x)` | $O(\log N)$ |
| `find(x)` | $O(\log N)$ |
| `count(x)` | $O(\log N)$ |
| `lower_bound(x)` | $O(\log N)$ |

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
set<int> s = {3, 1, 4, 1, 5, 9};
// s = {1, 3, 4, 5, 9}  (único + ordenado)

s.insert(2);        // s = {1, 2, 3, 4, 5, 9}
s.erase(3);         // s = {1, 2, 4, 5, 9}

cout << s.count(4); // 1 (existe)
cout << s.count(7); // 0 (não existe)

// Primeiro elemento >= 4
auto it = s.lower_bound(4);
cout << *it;        // 4

// Iterar em ordem crescente
for (int x : s) cout << x << ' ';

// multiset: permite repetições
multiset<int> ms = {1, 1, 2, 3};
ms.erase(ms.find(1)); // remove só UMA ocorrência de 1
// ms = {1, 2, 3}
```

</div>
