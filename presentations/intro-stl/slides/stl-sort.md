---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Algoritmos — Ordenação

Os algoritmos da STL operam em **ranges** — pares de iteradores `(begin, end)` que definem o intervalo de atuação.

| Algoritmo | O que faz | Custo |
|---|---|---|
| `sort(b, e)` | Ordena crescente | $O(N \log N)$ |
| `sort(b, e, cmp)` | Ordena com comparador | $O(N \log N)$ |
| `reverse(b, e)` | Inverte o range | $O(N)$ |
| `unique(b, e)` | Remove adj. duplicados | $O(N)$ |
| `next_permutation` | Próxima permutação lexicográfica | $O(N)$ |

**Dica:** Para remover **todos** os duplicados de um vector, use `sort` + `unique` + `erase`.

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
vector<int> v = {3, 1, 4, 1, 5, 9, 2, 6};

// Ordenar crescente
sort(v.begin(), v.end());
// v = {1, 1, 2, 3, 4, 5, 6, 9}

// Remover duplicatas
sort(v.begin(), v.end());
v.erase(unique(v.begin(), v.end()), v.end());
// v = {1, 2, 3, 4, 5, 6, 9}

// Ordenar decrescente
sort(v.begin(), v.end(), greater<int>());

// Comparador customizado
sort(v.begin(), v.end(), [](int a, int b) {
    return a > b;
});

// Gerar todas as permutações
string s = "abc";
do {
    cout << s << '\n';
} while (next_permutation(s.begin(), s.end()));
```

</div>

<style>
table td:nth-child(2) { font-size: 0.75em; }
</style>
