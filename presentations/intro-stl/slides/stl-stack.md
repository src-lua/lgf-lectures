---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Pilha `stack<T>`

**O que é?** Pilha LIFO — o último elemento inserido é o primeiro a sair.

**Quando usar?** DFS iterativo, verificação de parênteses balanceados, avaliação de expressões.

**Observação:** Não tem iteradores — só acesso ao topo com `top()`.

| Operação | Custo |
|---|---|
| `push(x)` | $O(1)$ |
| `pop()` | $O(1)$ |
| `top()` | $O(1)$ |
| `empty()`, `size()` | $O(1)$ |

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
stack<int> s;

s.push(10);
s.push(20);
s.push(30);

cout << s.top();  // 30 (topo da pilha)
cout << s.size(); // 3

s.pop();          // remove o topo
cout << s.top();  // 20

s.pop();
cout << s.top();  // 10

// Esvaziar (não tem iterador)
while (!s.empty()) {
    cout << s.top() << ' '; // 10
    s.pop();
}
```

</div>
