---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Hora de codar

**[CSES 1646 — Static Range Sum Queries](https://cses.fi/problemset/task/1646)**

Dado um array de $N$ inteiros e $Q$ queries, cada query pede a soma $A[l..r]$.

**Constraints:** $1 \le N, Q \le 2 \times 10^5$; $1 \le A_i \le 10^9$

**Atenção:** entrada 1-indexada — ajuste os índices!

**Dica:** use `long long` — a soma pode chegar a $2 \times 10^{14}$.

::right::

<div style="transform: translateY(-1.5rem)">

**Entrada**

```
8 4
3 1 4 1 5 9 2 6
3 6
1 8
2 5
4 7
```

**Saída**

```
19
31
11
17
```

</div>
