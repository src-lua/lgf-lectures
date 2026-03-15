---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Motivação — Soma de Intervalo

**Problema:** dado um array $A$ de $N$ inteiros e $Q$ consultas, cada consulta pede a soma $A[l] + A[l+1] + \cdots + A[r]$.

**Solução ingênua:** para cada query, percorrer o intervalo $[l, r]$.

- Custo por query: $O(N)$
- Custo total: $O(NQ)$

Para $N = Q = 10^5$: **$10^{10}$ operações** → TLE garantido!

**Podemos fazer melhor?** Sim — pré-computamos uma única vez e respondemos cada query em $O(1)$.

::right::

<div style="transform: translateY(-1.5rem)">

**Exemplo:**

```
A = [3, 1, 4, 1, 5, 9, 2, 6]
      0  1  2  3  4  5  6  7
```

Queries:
- Soma de $A[2..5]$ = $4+1+5+9 = 19$
- Soma de $A[0..3]$ = $3+1+4+1 = 9$
- Soma de $A[4..7]$ = $5+9+2+6 = 22$

Com solução ingênua: 3 percursos separados.

Com Prefix Sum: pré-processa **uma vez**, responde as 3 queries instantaneamente.

</div>
