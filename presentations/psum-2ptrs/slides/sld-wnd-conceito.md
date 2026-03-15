---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Sliding Window — Janela Deslizante

**Ideia:** manter um subarray (janela) de tamanho **fixo** $K$ deslizando da esquerda para a direita. A cada passo, remove o elemento que sai e adiciona o que entra — $O(1)$ por passo, $O(N)$ total.

**Janela fixa de tamanho K:**

```
A = [3, 1, 4, 1, 5, 9, 2, 6]   K = 3

janela [0..2]: soma = 8
janela [1..3]: soma = 6   (remove 3, adiciona 1)
janela [2..4]: soma = 10  (remove 1, adiciona 5)
...
```

**Quando usar janela fixa vs. variável?**

- **Fixa:** problema pede algo sobre todos os subarrays de tamanho exato $K$
- **Variável (Two Pointers):** problema tem restrição de soma/contagem e tamanho não fixo

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
// Máxima soma de subarray de tamanho K
int soma = 0, maxSoma = 0;

// Inicializa a primeira janela
for (int i = 0; i < k; i++)
    soma += a[i];

maxSoma = soma;

// Desliza: remove a[i-k], adiciona a[i]
for (int i = k; i < n; i++) {
    soma += a[i] - a[i - k];
    maxSoma = max(maxSoma, soma);
}

cout << maxSoma << '\n';
```

**Janela com estrutura auxiliar** (máximo da janela):

```cpp
// Usar deque para máximo em janela deslizante
deque<int> dq; // guarda índices

for (int i = 0; i < n; i++) {
    while (!dq.empty() && dq.front() < i - k + 1)
        dq.pop_front();  // fora da janela
    while (!dq.empty() && a[dq.back()] <= a[i])
        dq.pop_back();   // inútil
    dq.push_back(i);
    if (i >= k - 1)
        cout << a[dq.front()] << ' ';  // máximo
}
```

</div>
