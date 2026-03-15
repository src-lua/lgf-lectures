---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Hora de codar

**[CSES 1633 — Subarray Divisibility](https://cses.fi/problemset/task/1633)**

Dado um array de $N$ inteiros, conte quantos subarrays têm soma divisível por $N$.

**Constraints:** $1 \le N \le 2 \times 10^5$; $-10^9 \le A_i \le 10^9$

**Dica:** use Prefix Sum + contagem de restos (módulo). Dois prefixos com o mesmo resto $\mod N$ definem um subarray com soma divisível por $N$.

**Alternativa mais simples (aquecimento):**

**[CSES 1640 — Sum of Two Values](https://cses.fi/problemset/task/1640)** — encontre dois elementos com soma $= T$ usando Two Pointers em array ordenado.

::right::

<div style="transform: translateY(-1.5rem)">

**Entrada (Sum of Two Values)**

```
4 8
3 1 4 1
```

**Saída**

```
3 4
```

*(índices 1-indexados dos dois elementos)*

**Entrada (Subarray Divisibility)**

```
5
3 1 2 7 4
```

**Saída**

```
1
```

</div>
