---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Fila prioritária `priority_queue<T>`

**O que é?** Fila de prioridade — sempre acessa o **maior** elemento em $O(1)$.

**Internamente:** max-heap (árvore binária de máximo).

**Quando usar?** Dijkstra, encontrar o k-ésimo maior, processamento guloso por prioridade.

| Operação | Custo |
|---|---|
| `push(x)` | $O(\log N)$ |
| `pop()` | $O(\log N)$ |
| `top()` | $O(1)$ |
| `empty()`, `size()` | $O(1)$ |

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
// Max-heap (padrão)
priority_queue<int> pq;
pq.push(5); pq.push(1); pq.push(8);

cout << pq.top(); // 8
pq.pop();
cout << pq.top(); // 5

// Min-heap — inverter o comparador
priority_queue<int, vector<int>,
                   greater<int>> minpq;

minpq.push(5); minpq.push(1); minpq.push(3);

cout << minpq.top(); // 1

// Com pares — ordena pelo primeiro elemento
priority_queue<pair<int, int>> pq2;
pq2.push({10, 1});
pq2.push({5,  2});

cout << pq2.top().first; // 10
```

</div>

<style>
h1 { white-space: nowrap; }
</style>
