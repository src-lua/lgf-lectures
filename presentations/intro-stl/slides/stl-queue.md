---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Fila `queue<T>`

**O que é?** Fila FIFO — o primeiro elemento inserido é o primeiro a sair.

**Quando usar?** BFS (Busca em Largura), processamento de tarefas em ordem de chegada.

**Observação:** Não tem iteradores — só acesso à frente (`front()`) e ao final (`back()`).

| Operação | Custo |
|---|---|
| `push(x)` | $O(1)$ |
| `pop()` | $O(1)$ |
| `front()` | $O(1)$ |
| `back()` | $O(1)$ |
| `empty()`, `size()` | $O(1)$ |

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
queue<int> q;

q.push(10);
q.push(20);
q.push(30);

cout << q.front(); // 10 (primeiro a entrar)
cout << q.back();  // 30 (último a entrar)
cout << q.size();  // 3

q.pop();           // remove o front
cout << q.front(); // 20

q.pop();
cout << q.front(); // 30

// Processar todos em ordem de chegada
while (!q.empty()) {
    cout << q.front() << ' '; // 30
    q.pop();
}
```

</div>
