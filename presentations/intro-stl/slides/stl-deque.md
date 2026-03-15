---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Fila dupla `deque<T>`

**O que é?** Fila duplamente terminada — inserção e remoção em $O(1)$ nas **duas extremidades**.

**Quando usar?** Sliding window monotônico, quando precisa de push/pop em ambas as pontas.

**Observação:** Mais lento que `vector` para acesso aleatório e iteração, mas suporta `push_front` e `pop_front` em $O(1)$.

| Operação | Custo |
|---|---|
| `push_back(x)` / `push_front(x)` | $O(1)$ |
| `pop_back()` / `pop_front()` | $O(1)$ |
| `d[i]` | $O(1)$ |
| `size()` | $O(1)$ |

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
deque<int> d;

d.push_back(10);   // d = [10]
d.push_back(20);   // d = [10, 20]
d.push_front(5);   // d = [5, 10, 20]

cout << d.front(); // 5
cout << d.back();  // 20
cout << d.size();  // 3
cout << d[1];      // 10 (acesso por índice)

d.pop_front();     // remove da frente → d = [10, 20]
d.pop_back();      // remove do fim   → d = [10]

// Iterar normalmente
for (int x : d) cout << x << ' ';
```

</div>
