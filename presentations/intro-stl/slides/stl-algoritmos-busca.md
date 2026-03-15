---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Algoritmos — Busca e Utilidades

| Algoritmo | O que faz | Custo |
|---|---|---|
| `lower_bound` | Primeiro ≥ x | $O(\log N)$ |
| `upper_bound` | Primeiro > x | $O(\log N)$ |
| `binary_search` | Existe x? | $O(\log N)$ |
| `find` | Primeiro x | $O(N)$ |
| `count` | Quantos x? | $O(N)$ |
| `min` / `max` | Mínimo / máximo | $O(1)$ |
| `min_element` | Iterador para o mínimo / máximo | $O(N)$ |
| `accumulate` | Soma (ou redução) do range | $O(N)$ |

**Atenção:** `lower_bound`/`upper_bound` exigem container **ordenado**.

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
vector<int> v = {1, 2, 3, 5, 5, 5, 7};

// Busca binária — requer vetor ordenado!
auto lo = lower_bound(v.begin(), v.end(), 5);
auto hi = upper_bound(v.begin(), v.end(), 5);

cout << *lo;         // 5  (1º >= 5)
cout << (hi - lo);   // 3  (quantos 5s)

bool tem = binary_search(v.begin(), v.end(), 3); // true

auto it = find(v.begin(), v.end(), 5); // Busca linear
if (it != v.end()) cout << *it; // 5

int qtd = count(v.begin(), v.end(), 5); // 3

cout << min(3, 7);   // 3
cout << max(3, 7);   // 7

cout << *min_element(v.begin(), v.end()); // 1
cout << *max_element(v.begin(), v.end()); // 7

// Soma todos os elementos (init = 0)
int soma = accumulate(v.begin(), v.end(), 0LL); // 26
```

</div>

<style>
table td:nth-child(2) { font-size: 0.75em; }
</style>
