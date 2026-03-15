---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Hora de codar

**[CSES 1652 — Forest Queries](https://cses.fi/problemset/task/1652)**

Dada uma grade $N \times N$ onde cada célula é `*` (árvore) ou `.` (vazio), responda $Q$ queries: quantas árvores há no retângulo $(y_1, x_1)$ a $(y_2, x_2)$?

**Constraints:** $1 \le N \le 1000$; $1 \le Q \le 2 \times 10^5$

**Dica:** trate `*` como 1 e `.` como 0. Construa o Prefix Sum 2D e responda cada query em $O(1)$.

**Atenção:** entrada 1-indexada.

::right::

<div style="transform: translateY(-1.5rem)">

**Entrada**

```
4 3
.*.*
**..
*...
....
2 2 3 4
1 1 2 4
1 1 4 4
```

**Saída**

```
2
4
5
```

</div>
