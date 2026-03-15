---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Qual container usar?

<div style="transform: translateY(-1.5rem)">

| Precisa de... | Use |
|---|---|
| Lista com índice aleatório | `vector<T>` |
| Texto / sequência de chars | `string` |
| Tamanho fixo | `array<T,N>` |
| LIFO (pilha) | `stack<T>` |
| FIFO (fila) | `queue<T>` |
| Alteração duas pontas | `deque<T>` |
| Elementos únicos | `set<T>` |
| Contagem / chave→valor | `map<K,V>` |
| Lookup O(1) | `unordered_map<K,V>` |
| Maior/menor elemento | `priority_queue<T>` |

</div>

::right::

**Dúvida entre `map` e `unordered_map`?**
Prefira `map`: Por mais que unordered_map seja $O(1)$ médio, os setters tendem a forçar colisão, degradando pra $O(n)$. Use `unordered_map` somente se tiver certeza que não vai é possível forçar colisão.

**Dúvida entre `vector` e `array`?**
Prefira `array` se souber o tamanho. `array` é mais rápido porq evita o overhead de realocação e é mais cache-friendly. Use `vector` só se o tamanho for desconhecido em compilation time.
